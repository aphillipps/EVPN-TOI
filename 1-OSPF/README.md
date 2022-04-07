# LAB: OSPF Unnumbered as Underlay

## About

Goal of this lab: Configure OSPF Unnumbered

## Before you start the Labs


```cli
! Save the base configuration of all devices including Host1 and Host2
write

! Copy the startup config to another file
copy flash:startup-config flash:pre_lab1_config
```

## Configure OSPF unnumbered

__1. Configure the Loopback interfaces__

- Loopback0 is used for the router ID

- Loopback1 will be used in the next steps for the VTEP configuration

- Loopback2 is used for the OSPF unnumbered configuration

__2. Configure OSPF__

- VLAN 4093 is used an L3 link between the 2 peers for OSPF

- Disable spanning-tree for this VLAN and add it to a trunk group named LEAF_PEER_L3

- To speed up OSPF neighborship establishment use network type point-to-point

- Change the cost on the L3 peer-link so that the prefered path will always be the direct link to the Spine switches

- Several OSPF timers can be tweaked to improve convergence time in case of failures

- Authentication can be used

__3. Check OSPF__

```cli

show interface status

show ip interface brief

show ip ospf

show ip ospf neighbor

show ip ospf interfaces

show ip route

show ip route ospf

show ip ospf database router <IP address used as the link state ID>

```
