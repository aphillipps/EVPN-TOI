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

Leaf1 and Leaf2 are in the same MLAG domain named 12
Leaf3 and Leaf4 are in the same MLAG domain named 34

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

__2. Check OSPF__

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