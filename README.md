# NexaBank Enterprise Network Project

![Status](https://img.shields.io/badge/Status-In%20Progress-yellow)
![Phase](https://img.shields.io/badge/Current%20Phase-4%20Branch%20Connectivity-blue)
![Labs](https://img.shields.io/badge/Labs%20Complete-17%2F33-green)

---

## Overview

A complete enterprise network implementation for **NexaBank PLC**, a mid-sized commercial bank in Dhaka, Bangladesh. Built from scratch to mirror real-world bank and telecom infrastructure — covering network design, switching, routing, security, WAN connectivity, compliance and disaster recovery.

This is not a tutorial copy-paste project. Every design decision is justified with real engineering reasoning, aligned with Bangladesh Bank ICT Security Guidelines, ISO 27001 and NIST CSF. Where Packet Tracer hit platform limitations, each lab documents the full production configuration for real Cisco hardware alongside a working alternative implementation — demonstrating engineering judgement, not just lab completion.

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
| Firewall | Cisco ASA 5506-X | Cisco ASA 5505 / IOS ZBF on R1 |
| Core Switch (L3) | Cisco Cat 3650 | Cisco Cat 3650 |
| Access Switch (L2) | Cisco Cat 2960-X | Cisco Cat 2960 |
| Servers | Dell PowerEdge R340 | Generic Server |

---

## Project Phases

| Phase | Description | Labs | Status |
|-------|-------------|------|--------|
| Phase 1 | Network Design & Documentation | 01-03 | ✅ Complete |
| Phase 2 | Head Office Core Network | 04-10 | ✅ Complete |
| Phase 3 | Security Implementation | 11-17 | ✅ Complete |
| Phase 4 | Branch Connectivity | 18-22 | 🔄 In Progress |
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

### ✅ Phase 3 — Security Implementation
| Lab | Title | Key Deliverable |
|-----|-------|----------------|
| 11 | Advanced ACLs | Port/protocol-based filtering, department isolation |
| 12 | DMZ Architecture | WEB-SVR, ATM-GW, MAIL-SVR isolated from internal LAN |
| 13 | DHCP Server & Snooping | Centralised IP assignment, rogue DHCP prevention |
| 14 | Dynamic ARP Inspection | ARP spoofing / MITM attack prevention |
| 15 | 802.1X & TACACS+ | Identity-based port auth, device management auth |
| 16 | SSH Hardening | SSHv2, banners, timeouts on all HO devices |
| 17 | Zone-Based Firewall | Stateful inspection — INSIDE/OUTSIDE/DMZ zones |

---

## Engineering Approach to Platform Limitations

Several Phase 3 labs (13, 14, 15, 17) encountered genuine Cisco Packet Tracer platform constraints — not configuration errors. Rather than skip these topics, each lab documents:

1. **Full production configuration** for real Cisco hardware (verified against Cisco documentation)
2. **What was successfully demonstrated** in the PT simulation environment
3. **A working alternative implementation** covering an adjacent, equally relevant technology

This mirrors real-world engineering: working around tooling constraints while still delivering the required security outcome.

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
│   ├── NexaBank_HO_Lab11_ACL.pkt
│   ├── NexaBank_HO_Lab12_DMZ.pkt
│   ├── NexaBank_HO_Lab13_DHCP.pkt
│   ├── NexaBank_HO_Lab14_DAI.pkt
│   ├── NexaBank_HO_Lab15_802.1X.pkt
│   ├── NexaBank_HO_Lab15_TACACS.pkt
│   ├── NexaBank_HO_Lab16_SSH_Hardening.pkt
│   ├── NexaBank_HO_Lab17_ZBF.pkt
│   └── *_Notes.docx (full documentation + production configs + pop quizzes)
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
