# LAB: Multi Chassis LAG (MLAG)

## About

Goal of this lab: Configure MLAG

## Before you start the Labs


```cli
! Save the base configuration of all devices including Host1 and Host2
write

! Copy the startup config to another file
copy flash:startup-config flash:pre_lab0_config

```

## Configure MLAG

> Only Leaf* devices are part of this lab.

__1. Configure the MLAG Peer-Link__

- Use Port-channel 2000 for the Peer-link

- VLAN 4094 is used over the MLAG peer-link for peer connectivity

- Disable spanning-tree for this VLAN and add it to a trunk group named MLAG

Reminder: refer to the [first page](https://github.com/aphillipps/EVPN-TOI) for the IP addresses

__2. Configure the MLAG Domain__

- Leaf1 and Leaf2 are in the same MLAG domain named 12

- Leaf3 and Leaf4 are in the same MLAG domain named 34

__3. Check the MLAG Domains__

```cli

show mlag

show mlag detail

show mlag config-sanity

show vlan trunk group

show port-channel

show interface port-Channel 2000

show interface port-Channel 2000 trunk

```
