# NexaBank Enterprise Network Project

![Status](https://img.shields.io/badge/Status-In%20Progress-yellow)
![Phase](https://img.shields.io/badge/Current%20Phase-3%20Security-blue)
![Labs](https://img.shields.io/badge/Labs%20Complete-10%2F33-green)

---

## Overview

A complete enterprise network implementation for **NexaBank PLC**, a mid-sized commercial bank in Dhaka, Bangladesh. Built from scratch to mirror real-world bank and telecom infrastructure — covering network design, switching, routing, security, WAN connectivity, compliance and disaster recovery.

This is not a tutorial copy-paste project. Every design decision is justified with real engineering reasoning, aligned with Bangladesh Bank ICT Security Guidelines, ISO 27001 and NIST CSF.

---

## Organisation

| Site | Location | Staff |
|------|----------|-------|
| Head Office | Motijheel, Dhaka | ~300 |
| Branch 1 | Gulshan, Dhaka | ~100 |
| Branch 2 | Uttara, Dhaka | ~100 |

- **Total:** 500 employees across 3 locations
- **Regulated by:** Bangladesh Bank
- **Services:** Retail banking, corporate banking, online banking, ATM network

---

## Network Architecture

### IP Addressing Scheme
| Site | Range | Purpose |
|------|-------|---------|
| Head Office | 10.1.x.x | All HO departments |
| Branch 1 | 10.2.x.x | All BR1 departments |
| Branch 2 | 10.3.x.x | All BR2 departments |
| WAN Zone | 10.9.x.x | Point-to-point WAN links |

### VLAN Design
| VLAN | Name | Subnet |
|------|------|--------|
| 10 | Management | 10.x.10.0/27 |
| 20 | IT | 10.x.20.0/26 |
| 30 | Finance | 10.x.30.0/25 |
| 40 | HR | 10.x.40.0/27 |
| 50 | Tellers | 10.x.50.0/26 |
| 60 | DMZ | 10.x.60.0/28 |
| 70 | Operations | 10.x.70.0/27 |

### Device Selection
| Role | Real World | Packet Tracer |
|------|-----------|---------------|
| Core Router | Cisco ISR 4331 | Cisco ISR 4331 |
| Firewall | Cisco ASA 5506-X | Cisco ASA 5505 |
| Core Switch (L3) | Cisco Cat 3650 | Cisco Cat 3650 |
| Access Switch (L2) | Cisco Cat 2960-X | Cisco Cat 2960 |
| Servers | Dell PowerEdge R340 | Generic Server |

---

## Project Phases

| Phase | Description | Labs | Status |
|-------|-------------|------|--------|
| Phase 1 | Network Design & Documentation | 01-03 | ✅ Complete |
| Phase 2 | Head Office Core Network | 04-10 | ✅ Complete |
| Phase 3 | Security Implementation | 11-17 | 🔄 In Progress |
| Phase 4 | Branch Connectivity | 18-22 | ⏳ Pending |
| Phase 5 | Advanced Services | 23-27 | ⏳ Pending |
| Phase 6 | Compliance & Documentation | 28-30 | ⏳ Pending |
| Phase 7 | Final Integration | 31-33 | ⏳ Pending |

---

## Completed Labs

### ✅ Phase 1 — Foundation & Design
| Lab | Title | Key Deliverable |
|-----|-------|----------------|
| 01 | Network Design & Documentation | Full topology diagram (draw.io) |
| 02 | IP Addressing & Subnetting | Complete IP plan (Google Sheets) |
| 03 | Device Selection & Rack Design | HO rack diagram with justification |

### ✅ Phase 2 — Head Office Core Network
| Lab | Title | Key Deliverable |
|-----|-------|----------------|
| 04 | Core Switch Configuration | CS1 — VLANs, SVIs, inter-VLAN routing |
| 05 | Access Layer Switches | AS1-3 — port mapping, port security |
| 06 | Spanning Tree Protocol (RSTP) | CS1 root bridge, dual uplink redundancy |
| 07 | EtherChannel (LACP) | Po1/Po2/Po3 — link aggregation |
| 08 | Router Configuration & WAN | R1 — LAN/WAN interfaces, routing |
| 09 | NAT & Internet Access | PAT — 500 devices, single public IP |
| 10 | OSPF Multi-Area | Dynamic routing, self-healing network |

---

## Technologies Used

- **Simulation:** Cisco Packet Tracer 8.2.1
- **Diagramming:** draw.io
- **IP Planning:** Google Sheets
- **Version Control:** GitHub
- **All tools free** — no paid software used

---

## Compliance Alignment

| Standard | Application |
|----------|------------|
| ISO 27001 | A.9 Access Control, A.11 Physical Security, A.13 Network Controls, A.17 Redundancy |
| NIST CSF | PR.AC, PR.PT, PR.DS, DE.CM, RS.RP |
| Bangladesh Bank ICT Guidelines | Network segmentation, access control, availability, audit logging |

---

## Repository Structure

```
NexaBank-Enterprise-Network/
├── README.md
├── Phase-1-Design/
│   ├── nexabank_topology_v1.png
│   ├── nexabank_HO_rack_design_v1.png
│   └── NexaBank_IP_Addressing_Plan.xlsx
├── Phase-2-Head-Office/
│   ├── NexaBank_HO_Lab04_CoreSwitch.pkt
│   ├── NexaBank_HO_Lab05_AccessSwitches.pkt
│   ├── NexaBank_HO_Lab06_SpanningTree.pkt
│   ├── NexaBank_HO_Lab07_EtherChannel.pkt
│   ├── NexaBank_HO_Lab08_Router.pkt
│   ├── NexaBank_HO_Lab09_NAT.pkt
│   └── NexaBank_HO_Lab10_OSPF.pkt
├── Phase-3-Security/
├── Phase-4-Branch-Connectivity/
├── Phase-5-Advanced-Services/
├── Phase-6-Compliance/
└── Phase-7-Final-Integration/
```

---

## Author

**Asfi Ahmed**
IT Graduate, IIUM (International Islamic University Malaysia)
Dhaka, Bangladesh

> *"Built to hire — not just to learn."*
