# GRC Risk Register — Summary

> The full working spreadsheet (with live formulas, dropdowns, and the complete 93-control Annex A reference) is [GRC_Risk_Register.xlsx](GRC_Risk_Register.xlsx) — GitHub's built-in preview doesn't render `.xlsx` files reliably, so this page shows the same content as plain tables for quick viewing. Download the spreadsheet to see the risk scoring formulas and Annex A lookups in action.

## Assets

| Asset ID | Asset Name | Description | Category | Owner | Location |
|---|---|---|---|---|---|
| AST-001 | Proxmox host (minipc) | Hypervisor running Eramba, SQL sandbox, and lab VMs | Hardware / Server | Home lab admin | Server Cupboard |
| AST-002 | Flint 2 Router - GL-MT6000 | Home router providing internet access to the property | Hardware | Home lab admin | Server Cupboard |
| AST-003 | ONT fibre box | FTTP connection box | Hardware | Home lab admin / Internet provider | Server Cupboard |
| AST-004 | Adguard on Proxmox | Adguard running on Proxmox, providing ad and malware blocking services | Software | Home lab admin | MiniPC |

## Risks

Risk Score = Likelihood x Impact. Rating: 1-4 Low | 5-9 Medium | 10-14 High | 15-25 Critical.

| Risk ID | Asset ID | Risk Description | Likelihood | Impact | Score | Rating | Owner |
|---|---|---|---|---|---|---|---|
| RSK-001 | AST-002 | Router firmware bug causes loss of network segmentation, exposing lab systems to the main LAN | 2 | 4 | 8 | Medium | Home lab admin |
| RSK-002 | AST-001 | Hardware failure of the Proxmox host (MiniPC) resulting in loss of hosted services | 2 | 4 | 8 | Medium | Home lab admin |
| RSK-003 | AST-004 | Adguard stops running for multiple reasons | 2 | 1 | 2 | Low | Home lab admin |

## Controls

Each control is mapped to a real ISO/IEC 27001:2022 Annex A control and the risk it treats.

| Control ID | Annex A Control | Control Name | Treats | Implementation | Status | Evidence |
|---|---|---|---|---|---|---|
| CTL-001 | A.8.22 | Segregation of networks | RSK-001 | Lab VMs isolated on a dedicated internal Proxmox bridge (vmbr1) with no physical uplink; NAT egress only, no inbound access from main LAN except via SSH tunnel | Implemented | Verified 30 Aug 2026: main-LAN device cannot reach 10.10.10.x directly; Eramba reachable only via SSH tunnel |
| CTL-002 | A.7.13 | Equipment maintenance | RSK-002 | Carrying out periodic tasks such as renewing thermal paste and general dusting of the unit | Implemented | Proxmox dashboard available for verification |
| CTL-003 | A.8.23 | Web filtering | RSK-003 | A backup instance of AdGuard runs alongside the primary; should the primary fail, the secondary takes over | Implemented | Can view the dashboard to observe both AdGuard instances installed and running |

See [network-segmentation.md](../network-segmentation/network-segmentation.md) for the full write-up behind CTL-001.
