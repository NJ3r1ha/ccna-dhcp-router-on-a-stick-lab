# Troubleshooting Process – DHCP Router-on-a-Stick Lab

## Problem Description
Inter-VLAN communication was not working.  
Only hosts in VLAN 99 were able to reach their default gateway.

## Layer 1 – Physical
All switch interfaces were in *connected* state, therefore Layer 1 issues were excluded.

## Layer 2 – VLANs and Trunking
VLANs 10, 20, 30 and 99 were correctly assigned to access ports.  
The trunk interface was only allowing VLANs 30 and 99, which prevented VLANs 10 and 20 from reaching the router.

Relevant command:
show interfaces trunk

## Layer 3 – Inter-VLAN Routing
Subinterface G0/0.20 had no IP address configured.  
Subinterface G0/0.30 had incorrect VLAN encapsulation.

Relevant commands:

show ip interface brief
show ip route


## DHCP
- DHCP pool for VLAN 30 was missing
- DHCP pool for VLAN 20 had incorrect default-router configuration

Relevant command:

show running-config | section dhcp

## Resolution
- Allowed VLANs 10 and 20 on trunk interface
- Configured correct encapsulation and IP address on G0/0.20
- Corrected encapsulation on G0/0.30
- Created DHCP pool for VLAN 30
- Fixed default-router configuration in POOL_20

## Result
All hosts successfully obtained IP addresses via DHCP and full inter-VLAN connectivity was restored.
