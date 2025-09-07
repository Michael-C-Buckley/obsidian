
## Basic Address Configuration

```
set interface ge-0/0/0.0 family inet address 10.0.12.1/24
```

* All interfaces must have a unit selected, `.0` for the "base" untagged version works on L3
* `inet` is IPv4 reference (from BSD)


### Basic OSPF

```
# To enter subconfig
edit protocols ospf area 0.0.0.0

```