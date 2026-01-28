# ccna-dhcp-router-on-a-stick-lab
Multi-VLAN DHCP troubleshooting lab using Router-on-a-Stick

# DHCP Router-on-a-Stick Troubleshooting Lab

## Overview
This lab demonstrates a multi-VLAN network using Router-on-a-Stick, where the router acts as both
an inter-VLAN router and a DHCP server. Multiple intentional misconfigurations were introduced
and resolved using a structured troubleshooting approach.

## Topology
- 1 Router
- 1 Switch
- 4 PCs
- VLANs: 10 (Users), 20 (IT), 30 (Servers), 99 (Management)

## IP Addressing
| VLAN | Subnet |
|----|----|
| 10 | 192.168.10.0/24 |
| 20 | 192.168.20.0/24 |
| 30 | 192.168.30.0/24 |
| 99 | 192.168.99.0/24 |

## Troubleshooting Summary
- Trunk interface allowed only VLANs 30 and 99
- Subinterface G0/0.20 missing IP address and encapsulation
- Subinterface G0/0.30 had incorrect VLAN encapsulation
- DHCP pool for VLAN 30 was missing
- DHCP pool for VLAN 20 had incorrect default-router configuration

## Resolution
All Layer 2, Layer 3 and DHCP configuration issues were resolved.  
All hosts successfully obtained IP addresses via DHCP and full inter-VLAN connectivity was restored.

## Tools
- Cisco Packet Tracer
- Cisco IOS CLI
