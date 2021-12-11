# LAB: iBGP as Overlay

## About

Goal of this lab: Configure iBGP as Overlay

## Configure iBGP EVPN Sessions

Spine1 and Spine2 are route-reflectors

Spine1 and Spine2 have the same cluster ID

Leaf1-4 are route-reflector clients

## Check the iBGP EVPN Sessions

```cli

show bgp neighbors

show bgp evpn summary

show bgp evpn

```

Note that in order to not activate BGP sessions on IPv4 by default, there are 2 choices:

1. Configure "no bgp default ipv4-unicast" under router

2. Desactivate IPv4 when not wanted for each peer and/or neighbor under the IPv4 address-family as in the example below:

```cli

router bgp 65000
   address-family ipv4
      no neighbor EVPN-OVERLAY-PEERS activate

```

In thconfiguration files of this lab, both have been done, but one of the 2 choices is sufficient.