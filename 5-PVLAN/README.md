# LAB: PVLAN

## About

Goal of this lab: Configure PVLAN services on an EVPN/VXLAN Leaf/Spine Architecture and understand the associated EVPN route-types

## Configure a PVLAN Domain on Leaf switches

Configure a private VLAN Domain on Leaf switches 1 to 4 as follows:
- VLAN 10: primary VLAN
- VLAN 111: Isolated VLAN
- VLAN 112: Community VLAN 1
- VLAN 113: Community VLAN 2

## Extend the PVLAN Domain across the Fabric

__1. Configure the MAC VRF for each VLAN__

__2. Configure the VLAN to VNI mapping on the VXLAN interfaces__


## Check connectivity between Host1 and Host2

Ping Host1 from Host2 and vice-versa

As both hosts are in the same community VLAN, you should be able to communicate.

## Check MAC address tables, VLANs, EVPN routes and VXLAN outputs

```cli

show vlan

show vlan private-vlan

show mac address-table

show vxlan flood vtep

show vxlan address-table

show bgp evpn route-type imet

show bgp evpn route-type mac-ip detail

```

You can also do some tcpdumps for the generated pings to check the VNI of the encapsulated traffic.


## Change VLAN for Host1

Configure host1 in a different VLAN (community 2 or isolated) and test connectivity again.