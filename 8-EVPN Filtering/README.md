# LAB: EVPN Filtering

## About

Goal of this lab: Filter EVPN routes and inject a default route

## Before you start the Labs


```cli
! Save the base configuration of all devices including Host1 and Host2
write

! Copy the startup config to another file
copy flash:startup-config flash:pre_lab8_config

```

## Configure a default route

Configure a EVPN default route

Inject it in the VRF named TEST from Leaf 1 and Leaf 2 (EVPN GWs)

Filter out all the other RT-5 routes announced to the local domain frm the EVPN GWs

Still announce all th RT-2 and RT-3 to the local domain from the EVPN GWs

## Configure SoO filters on Leaf1 and Leaf2 for the routes announced to the local POD


## Check EVPN routes and VRF routing table


```cli

show bgp evpn

show bgp evpn route-type ip-prefix ipv4

show bgp evpn route-type ip-prefix ipv4 domain local

show bgp evpn route-type ip-prefix ipv4 domain remote

show ip route vrf TEST

```