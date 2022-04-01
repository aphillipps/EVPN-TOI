# LAB: OSPF Unnumbered as Underlay

## About

Goal of this lab: Configure MLAG and OSPF Unnumbered

## Before you start the Labs


```cli
# Save the base configuration of all devices including Host1 and Host2

write

# Copy the startup config to another file

copy flash:startup-config flash:initial_config

```

## Configure MLAG

Leaf1 and Leaf2 are in the same MLAG domain named 12.

Leaf3 and Leaf4 are in the same MLAG domain named 34.

Use Port-channel 2000 for the peer-link.

VLAN 4094 is used over the MLAG peer-link for peer connectivity.

Disable spanning-tree for this VLAN and add it to a trunk group named MLAG.

Reminder: refer to the first page for the IP addresses.

__1. Configure the MLAG Peer-Link__

__2. Configure the MLAG Domain__

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

## Configure OSPF unnumbered

__1. Configure the Loopback interfaces__

__2. Configure OSPF__

Loopback0 is used as router ID.

Loopback2 is used for the OSPF unnumbered configuration.

Vlan 4093 is used an L3 link between the 2 peers for OSPF.

Disable spanning-tree for this VLAN and add it to a trunk group named LEAF_PEER_L3.

To speed up OSPF neighborship establishment use network type point-to-point.

Change the cost on the L3 peer-link so that the prefered path will always be the direct link to the Spine switches.

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
