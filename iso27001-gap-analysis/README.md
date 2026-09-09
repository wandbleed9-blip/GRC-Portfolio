# ISO/IEC 27001:2022 Gap Analysis — Summary

> The full working spreadsheet (with dropdowns and live dashboard formulas) is [ISO27001_Gap_Analysis.xlsx](ISO27001_Gap_Analysis.xlsx). GitHub doesn't render `.xlsx` previews reliably, so this page shows the same content as plain tables.

## Summary

All 93 Annex A controls (2022 revision) have been assessed against my home lab environment.

| Status | Count |
|---|---|
| Implemented | 6 |
| Partial | 9 |
| Not Implemented | 6 |
| Not Applicable | 72 |
| **Total controls** | **93** |

| Theme | Total | Implemented | Not Implemented |
|---|---|---|---|
| Organisational | 37 | 0 | 3 |
| People | 8 | 0 | 0 |
| Physical | 14 | 1 | 0 |
| Technological | 34 | 5 | 3 |

## Full control walkthrough

<details>
<summary>Click to expand all 93 Annex A controls</summary>

| Control ID | Theme | Control Name | Current State | Evidence / Notes | Gap Description | Priority | Remediation Plan |
|---|---|---|---|---|---|---|---|
| A.5.1 | Organisational | Policies for information security | Not Implemented | No policy has been written |  | Medium | Draft a policy |
| A.5.2 | Organisational | Information security roles and responsibilities | Not Applicable |  |  | N/A |  |
| A.5.3 | Organisational | Segregation of duties | Not Applicable |  |  | N/A |  |
| A.5.4 | Organisational | Management responsibilities | Not Applicable |  |  | N/A |  |
| A.5.5 | Organisational | Contact with authorities | Not Applicable |  |  | N/A |  |
| A.5.6 | Organisational | Contact with special interest groups | Not Applicable |  |  | N/A |  |
| A.5.7 | Organisational | Threat intelligence | Partial | Adguards dashboard offers some intelligence |  | Medium | Research and implement further threat intelligence capabilities possible for the homelab |
| A.5.8 | Organisational | Information security in project management | Not Applicable |  |  | N/A |  |
| A.5.9 | Organisational | Inventory of information and other associated assets | Partial | Basic inventory currently performed |  | Medium | Continue updating inventory |
| A.5.10 | Organisational | Acceptable use of information and other associated assets | Partial | Single user environment, acceptable use is implied |  | N/A |  |
| A.5.11 | Organisational | Return of assets | Not Applicable |  |  | N/A |  |
| A.5.12 | Organisational | Classification of information | Not Applicable |  |  | N/A |  |
| A.5.13 | Organisational | Labelling of information | Not Applicable |  |  | N/A |  |
| A.5.14 | Organisational | Information transfer | Not Applicable |  |  | N/A |  |
| A.5.15 | Organisational | Access control | Partial | Single user environment, only one person holds the credentials for the lab environment. SQL sandbox is only accessed throgh the proxmox environment. | No formal access policy exists. | N/A |  |
| A.5.16 | Organisational | Identity management | Not Applicable |  |  | N/A |  |
| A.5.17 | Organisational | Authentication information | Not Applicable |  |  | N/A |  |
| A.5.18 | Organisational | Access rights | Not Applicable |  |  | N/A |  |
| A.5.19 | Organisational | Information security in supplier relationships | Not Applicable |  |  | N/A |  |
| A.5.20 | Organisational | Addressing information security within supplier agreements | Not Applicable |  |  | N/A |  |
| A.5.21 | Organisational | Managing information security in the ICT supply chain | Not Applicable |  |  | N/A |  |
| A.5.22 | Organisational | Monitoring, review and change management of supplier services | Not Applicable |  |  | N/A |  |
| A.5.23 | Organisational | Information security for use of cloud services | Not Applicable |  |  | N/A |  |
| A.5.24 | Organisational | Information security incident management planning and preparation | Not Implemented |  | No incident response plan exists for the lab environment (e.g. what to do if segmentation fails or a lab VM is compromised). | Medium | Draft a short incident response outline: detection, containment, recovery, lessons-learned log. |
| A.5.25 | Organisational | Assessment and decision on information security events | Not Applicable |  |  | N/A |  |
| A.5.26 | Organisational | Response to information security incidents | Not Applicable |  |  | N/A |  |
| A.5.27 | Organisational | Learning from information security incidents | Not Applicable |  |  | N/A |  |
| A.5.28 | Organisational | Collection of evidence | Not Applicable |  |  | N/A |  |
| A.5.29 | Organisational | Information security during disruption | Not Applicable |  |  | N/A |  |
| A.5.30 | Organisational | ICT readiness for business continuity | Not Applicable |  |  | N/A |  |
| A.5.31 | Organisational | Legal, statutory, regulatory and contractual requirements | Not Applicable |  |  | N/A |  |
| A.5.32 | Organisational | Intellectual property rights | Not Applicable |  |  | N/A |  |
| A.5.33 | Organisational | Protection of records | Not Applicable |  |  | N/A |  |
| A.5.34 | Organisational | Privacy and protection of PII | Not Applicable |  |  | N/A |  |
| A.5.35 | Organisational | Independent review of information security | Not Applicable |  |  | N/A |  |
| A.5.36 | Organisational | Compliance with policies, rules and standards for information security | Not Applicable |  |  | N/A |  |
| A.5.37 | Organisational | Documented operating procedures | Not Implemented |  | No documented operating procedures exist yet for lab administration tasks (e.g. VM provisioning, network changes). | Medium | Write short SOPs for recurring lab admin tasks, starting with network changes given the risk demonstrated in RSK-001. |
| A.6.1 | People | Screening | Not Applicable |  |  | N/A |  |
| A.6.2 | People | Terms and conditions of employment | Not Applicable |  |  | N/A |  |
| A.6.3 | People | Information security awareness, education and training | Not Applicable |  |  | N/A |  |
| A.6.4 | People | Disciplinary process | Not Applicable |  |  | N/A |  |
| A.6.5 | People | Responsibilities after termination or change of employment | Not Applicable |  |  | N/A |  |
| A.6.6 | People | Confidentiality or non-disclosure agreements | Not Applicable |  |  | N/A |  |
| A.6.7 | People | Remote working | Not Applicable |  |  | N/A |  |
| A.6.8 | People | Information security event reporting | Not Applicable |  |  | N/A |  |
| A.7.1 | Physical | Physical security perimeters | Implemented | Equipment is stored in a locked building when unoccupied  |  | N/A |  |
| A.7.2 | Physical | Physical entry | Not Applicable |  |  | N/A |  |
| A.7.3 | Physical | Securing offices, rooms and facilities | Not Applicable |  |  | N/A |  |
| A.7.4 | Physical | Physical security monitoring | Not Applicable |  |  | N/A |  |
| A.7.5 | Physical | Protecting against physical and environmental threats | Not Applicable |  |  | N/A |  |
| A.7.6 | Physical | Working in secure areas | Not Applicable |  |  | N/A |  |
| A.7.7 | Physical | Clear desk and clear screen | Not Applicable |  |  | N/A |  |
| A.7.8 | Physical | Equipment siting and protection | Not Applicable |  |  | N/A |  |
| A.7.9 | Physical | Security of assets off-premises | Not Applicable |  |  | N/A |  |
| A.7.10 | Physical | Storage media | Not Applicable |  |  | N/A |  |
| A.7.11 | Physical | Supporting utilities | Not Applicable |  |  | N/A |  |
| A.7.12 | Physical | Cabling security | Not Applicable |  |  | N/A |  |
| A.7.13 | Physical | Equipment maintenance | Partial | No preventative maintainance schedule but maintainance will be carried out | no documented procedures | Low | Write SOP and schedule for when tasks are to be carried out |
| A.7.14 | Physical | Secure disposal or re-use of equipment | Not Applicable |  |  | N/A |  |
| A.8.1 | Technological | User endpoint devices | Not Applicable |  |  | N/A |  |
| A.8.2 | Technological | Privileged access rights | Not Applicable |  |  | N/A |  |
| A.8.3 | Technological | Information access restriction | Implemented | Console only access to the SQL environment, vmbr1 has no network access |  | N/A |  |
| A.8.4 | Technological | Access to source code | Not Applicable |  |  | N/A |  |
| A.8.5 | Technological | Secure authentication | Not Applicable |  |  |  |  |
| A.8.6 | Technological | Capacity management | Partial | Capacity can be monitored via the proxmox dashboard | No thresholds or alerts implemented | Medium | Implement automated monitoring and set up alerts for assessts nearing capacity. |
| A.8.7 | Technological | Protection against malware | Implemented | All systems have anti-malware software running, updates are pushed automatically |  | N/A |  |
| A.8.8 | Technological | Management of technical vulnerabilities | Not Applicable |  |  |  |  |
| A.8.9 | Technological | Configuration management | Not Implemented |  | No configuration backup/version control currently kept for router or Proxmox host configuration. | Medium | Export and version-control router config backups; document Proxmox host configuration. |
| A.8.10 | Technological | Information deletion | Not Applicable |  |  | N/A |  |
| A.8.11 | Technological | Data masking | Not Applicable |  |  |  |  |
| A.8.12 | Technological | Data leakage prevention | Not Applicable |  |  |  |  |
| A.8.13 | Technological | Information backup | Not Implemented |  | No backup strategy currently configured for lab VMs (Eramba, SQL sandbox) or their data. | High | Configure Proxmox scheduled backups (vzdump) for lab VMs with a defined retention period; document restore testing. |
| A.8.14 | Technological | Redundancy of information processing facilities | Not Applicable |  |  | N/A |  |
| A.8.15 | Technological | Logging | Not Implemented |  | logging not currently implemented | Medium | Re-establish remote syslog (or a lighter alternative) from the router to a lab log host once network changes stabilise. |
| A.8.16 | Technological | Monitoring activities | Partial | Some manual monitoring of dashboards is performed | Monitoring is done on an ad-hoc basis |  | Implement an automated monitoring solution |
| A.8.17 | Technological | Clock synchronization | Not Applicable |  |  | N/A |  |
| A.8.18 | Technological | Use of privileged utility programs | Not Applicable |  |  | N/A |  |
| A.8.19 | Technological | Installation of software on operational systems | Not Applicable |  |  | N/A |  |
| A.8.20 | Technological | Networks security | Partial | AdGuard Home used for DNS-based filtering/monitoring on the main LAN; router DHCP correctly points clients at it. | No equivalent DNS filtering currently applied to the isolated lab network's egress traffic. | Low | Point lab VM DNS at AdGuard or a second filtering resolver reachable via the NAT path. |
| A.8.21 | Technological | Security of network services | Implemented | Firewall configured with Adguard performing certain functions, router and endpoint based |  |  |  |
| A.8.22 | Technological | Segregation of networks | Implemented | The SQL sandbox on the isolated lab network (vmbr1) has no active network-based access. It is reached solely through the proxmox host console. | None — control is in place and verified. | Low |  |
| A.8.23 | Technological | Web filtering | Implemented | Adguard performs web filtering, all devices on the network are directed through Adguard by the router  |  | N/A |  |
| A.8.24 | Technological | Use of cryptography | Not Applicable |  |  | N/A |  |
| A.8.25 | Technological | Secure development life cycle | Not Applicable |  |  | N/A |  |
| A.8.26 | Technological | Application security requirements | Not Applicable |  |  | N/A |  |
| A.8.27 | Technological | Secure system architecture and engineering principles | Not Applicable |  |  |  |  |
| A.8.28 | Technological | Secure coding | Not Applicable |  |  |  |  |
| A.8.29 | Technological | Security testing in development and acceptance | Not Applicable |  |  |  |  |
| A.8.30 | Technological | Outsourced development | Not Applicable |  |  |  |  |
| A.8.31 | Technological | Separation of development, test and production environments | Partial | Environments will be segmented via proxmox | no documented procedure | Medium | Document procedure for setting up isolated and segmented environments. |
| A.8.32 | Technological | Change management | Not Applicable |  |  | N/A |  |
| A.8.33 | Technological | Test information | Not Applicable |  |  | N/A |  |
| A.8.34 | Technological | Protection of information systems during audit testing | Not Applicable |  |  | N/A |  |

</details>

See [network-segmentation.md](../network-segmentation/network-segmentation.md) for the detailed write-up behind the A.8.22 / A.8.3 entries.
