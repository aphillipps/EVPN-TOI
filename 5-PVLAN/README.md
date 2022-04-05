# LAB: PVLAN

## About

Goal of this lab:

- Configure PVLAN services on an EVPN/VXLAN Leaf/Spine Architecture

- Understand the associated EVPN route-types

## Before you start the Labs


```cli
! Save the base configuration of all devices including Host1 and Host2
write

! Copy the startup config to another file
copy flash:startup-config flash:pre_lab0_config

```

## Configure a PVLAN Domain on Leaf switches

Configure a private VLAN Domain on Leaf switches 1 to 4 as follows:

- VLAN 10: Primary VLAN

- VLAN 111: Isolated VLAN

- VLAN 112: Community VLAN 1

- VLAN 113: Community VLAN 2

## Extend the PVLAN Domain across the Fabric

__1. Configure the MAC VRF for each VLAN__

- Configure MAC VRFs for each of the 4 VLANs

Note that MAC addresses only need to be redistributed into the Primary VLAN of a PVLAN Domain

__2. Configure the VLAN to VNI mapping on the VXLAN interfaces__

- Configure VLAN to VNI mapping for all 4 VLANs using the VLAN ID as VNI

## Check connectivity between Host1 and Host2

- Ping Host1 from Host2 and vice-versa

As both hosts are in the same community VLAN, you should be able to communicate

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

You can also run some tcpdumps for the generated pings to check the VNI used for the the encapsulated traffic


## Change VLAN for Host1

- Configure Host1 in a different VLAN (community 2 or isolated) and test connectivity again

- Check the outputs above

- Run some tcpdumps and you will see that the VNI used for the encapsulation is the VNI of the source host

Note that you will be able to ping from Host1 to Host2 even if there are in different communities as PVLAN is not supported on vEOS , but you will at least see the switch encapsulation behaviour and the MAC address learning.
