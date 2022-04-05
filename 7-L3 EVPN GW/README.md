# LAB: L3 EVPN Gateway

## About

Goal of this lab: Understand L3 EVPN Gateways

## Before you start the Labs


```cli
! Save the base configuration of all devices including Host1 and Host2
write

! Copy the startup config to another file
copy flash:startup-config flash:pre_lab0_config

```

## Configure a VRF on all Leaf switches

Configure a VRF named TEST on Leaf 1 to 4 and on Host1

Configure an SVI for VLAN 10 on all switches above (172.16.112.1/24)

Configure an IP VRF under BGP

Map the VRF to VNI on the VXLAN interface

Configure additional Loopbacks on Leaf3 and Leaf4 in the TEST VRF

Configure additional Loopbacks on Host1 in the TEST VRF

## Configure Leaf1 and Leaf2 as an L3 EVPN GW


## Check MAC address tables, VLANs, EVPN routes and VXLAN outputs

Note that depending on the hashing, pings between the Loopbacks on Leaf3/Leaf4 and Host1 may or may not work

This is because there is no BGP peering between Leaf3 and Leaf4 inside the TEST VRF

Generate pings from Host2 so that you can see the host routes

```cli

show bgp evpn

show bgp evpn route-type ip-prefix ipv4

show bgp evpn route-type ip-prefix ipv4 domain local

show bgp evpn route-type ip-prefix ipv4 domain remote

show ip route vrf TEST

show vrf

```