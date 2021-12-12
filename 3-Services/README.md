# LAB: Services

## About

Goal of this lab: Configure services on an EVPN/VXLAN Leaf/Spine Architecture and understand the EVPN route-types

## Configure a VXLAN interface

Configure a VXLAN interface with Loopback 1 as source IP on Leaf switches 1 to 4

## Check the VXLAN interface

```cli

show interface vxlan1

```

## Configure a Layer 2 service across the Fabric

Configure VLAN 112

Configure Host1 and Host2 in VLAN 112

## Check connectivity between Host1 and Host2

Ping Host1 from Host2 and vice-versa

## Check EVPN routes and VXLAN outputs

```cli

show bgp neighbors

show bgp evpn summary

show bgp evpn

show bgp evpn neighbor <address of neighbor>

show bgp evpn route-type imet

show bgp evpn route-type mac-ip

show vxlan address-table

show mac address-table

show interface vxlan1

show vxlan vni

show bgp evpn instance

```
