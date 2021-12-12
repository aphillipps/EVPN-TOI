# LAB: L2 EVPN Gateway

## About

Goal of this lab: Understand L2 EVPN Gateways

## Configure Leaf1 and Leaf2 as L2 EVPN Gateways

Configure Leaf1 and Leaf2 as L2 EVPN Gateways

The existing Leaf/Spine Architecture is the EVPN local domain

Host1 will simulate the remote EVPN domain which is composed of one Leaf only in this lab

Configure different RDs and RTs for the remote domain



## Configure Host1 as a Leaf Switch part of the remote domain

__1. Configure eBGP as Underlay__

Configure eBGP as an underlay between Leaf1 and Leaf2 (on Ethernet interfaces 5 on the Leaf sides) and Host1 (on port-channel interfaces)


__2. Configure eBGP as Overlay__

Configure eBGP as an overlay between Leaf1 and Leaf2 and Host1


__3. Extend the existing VLANs to the remote domain__

Configure the MAC VRFs on Host1

Configure the VLAN to VNI mapping on Host1


## Check MAC address tables, VLANs, EVPN routes and VXLAN outputs

Generate traffic from host2 by ping the broadcast address in VLAN 112 t be able to interesting outputs

```cli

show bgp evpn

show bgp evpn summary

show bgp evpn route-type imet vni 10

show bgp evpn route-type mac-ip

show bgp evpn route-type imet

show bgp evpn route-type mac-ip detail

```