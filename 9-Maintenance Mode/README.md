# LAB: Maintenance Mode

## About

Goal of this lab: Understand and test Arista maintenance mode

## Before you start the Labs


```cli
! Save the base configuration of all devices including Host1 and Host2
write

! Copy the startup config to another file
copy flash:startup-config flash:pre_lab0_config

```

## Check underlay routes and OSPF database on switches

Check the underlay routing table (default VRF table)

See ECMP routes learned by Spine switches on the leaf switches

Check the metric of the announced OSPF routes

```cli

show ip route

show ip ospf database detail 10.0.0.1

```

## Coonfigure and enter maintenance mode on Spine1

Configure maintenance mode on Spine1

Enter maintenance mode on Spine1

```cli
config
maintenance
   unit ON-MM-UNIT
   quiesce
```


## Check underlay routes and OSPF database on switches

Check underlay routes and OSPF database on switches again and check that the metric has changed for the routes announced by Spine1

```cli

show ip route

show ip ospf database detail 10.0.0.1

show logging

show maintenance

```

## Save the configuration on Spine1 and reload it

Save the configuration so that Spine1 stays in maintenance mode after reload and reload it

```cli

write
reload

```

## Check underlay routes and OSPF database on switches

Just after the reload, check underlay routes and OSPF database on switches

```cli

show ip route

show ip ospf database detail 10.0.0.1

show maintenance

```

## Exit maintenance mode on Spine1

Exit maintenace mode on Spine1

```cli
config
maintenance
   unit ON-MM-UNIT
   no quiesce
```

## Check underlay routes and OSPF database on switches

Just after the reload, check underlay routes and OSPF database on switches

```cli

show ip route

show ip ospf database detail 10.0.0.1

show maintenance

shoow logging

```

## Test maintenance mode on Leaf3

Configure maintenance mode on Leaf3 and test it following the same procedure as for Spine1