# Home Lab Network Segmentation

**Control demonstrated:** ISO/IEC 27001:2022 Annex A.8.22 — Segregation of networks
**Related:** A.8.3 (Information access restriction), A.5.15 (Access control)

## The goal

My home lab (a Proxmox host running Eramba, a SQL sandbox, and other test VMs) shares a network with everyday household devices.

Having learned about network segmentation, I wanted to put it into practice with the lab environment. The lab needed to be able to access the internet but unreachable from the main network. It would only be reachable by the main network through a narrow, documented path.

## First attempt: router-level VLANs

My first approach was to segment at the router (a GL.iNet Flint 2), using its VLAN filtering to put a dedicated LAN port on its own VLAN, isolated from the rest of the network via firewall.

On paper the configuration was correct: a single clean VLAN definition, the lab port set untagged with the right PVID, the CPU port tagged, and a firewall zone denying LAN↔Lab traffic in both directions.

In practice though, it was let down by the router's interface. Carrying out the VLAN filtering required using advanced mode via LuCI. There appeared to be a misconfiguration or bug occurring when setting the VLAN definitions — in short, it would not allow one clean VLAN section but would duplicate them after saving. Removing the duplicates and applying the changes would then cause a timeout and roll back.

This issue then caused the bridge to fail entirely, dropping all LAN connectivity and forcing a full factory reset.

A further attempt was made via the command line over SSH, to bypass the web interface entirely. However, this approach ended with the same result — complete loss of connectivity and another factory reset.

It was clear that a different approach to segregation was needed.

## The pivot: host-level isolation

Rather than keep fighting a single point of failure that took down the whole network when it misbehaved, I moved the segmentation down a layer, onto the Proxmox host itself:

- Created a second virtual bridge (`vmbr1`) with **no physical network interface attached** — it exists purely inside the hypervisor, so lab VMs on it have no path to the physical LAN at all by default.
- Assigned the lab VMs (SQL sandbox, and others to follow) to `vmbr1` instead of the main bridge.
- Enabled IP forwarding and added NAT so lab VMs can reach the internet, with an explicit `FORWARD` rule permitting only established/related return traffic back into the lab — new *inbound* connections from the main network are never allowed.
- I use an SSH tunnel from my workstation through the Proxmox host into the lab network, rather than opening a standing firewall exception. Access exists only for the duration of an active, authenticated session.

## Verification

- A device on the main LAN cannot reach any address on the lab subnet directly — confirmed by attempted connection failure.
- A lab VM can reach the internet (`ping`, `apt update` succeed) via the NAT path.
- Services on the lab network are reachable only via the SSH tunnel, and only while that tunnel is active.

## Why this maps to A.8.22

Annex A.8.22 calls for network segregation based on risk criticality — critically, it doesn't prescribe *how*. This is a case where a documented risk-based decision (moving away from an unreliable enforcement mechanism toward a more robust one) is itself part of demonstrating the control, not just the final diagram. Being able to explain *why* a particular implementation was chosen — including a rejected alternative and the evidence for rejecting it — is the kind of reasoning an auditor actually wants to see, more so than a working config with no story behind it.

## Lessons learned

- Consumer router firmware is not always a dependable point for security controls, even when the configuration is textbook-correct.
- Segmentation enforced at the hypervisor level, with no physical uplink at all, removes an entire class of failure mode (a shared switch/router misbehaving) compared to VLAN tagging on shared hardware.
- Session-based access (SSH tunnel) over a standing firewall exception is a small extra step day-to-day, but keeps the access window explicit and time-bound.
