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
