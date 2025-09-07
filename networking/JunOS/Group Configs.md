
Groups can apply multiple config items at once:

```
set groups kelvinsucks interfaces <ge*> unit <*> description "Kelvin Sucks!!!"
set apply-groups kelvinsucks
wildcard range set interfaces ge-0/0/[\d+].0
```


Apply-paths for building dynamic prefix-lists:

```
set policy-options prefix-list kelvinsucks_bgp apply-path "protocols bgp group <*> neighbor <*>" 
```


Interface ranges can be used as well:

```
set interfaces interface-range KELVINSUCKS member ge-0/0/[4-6]      
set protocols rstp interface KELVINSUCKS 
```


[https://www.juniper.net/documentation/us/en/software/junos/cli/topics/topic-map/configuration-groups-usage.html](https://www.juniper.net/documentation/us/en/software/junos/cli/topics/topic-map/configuration-groups-usage.html "https://www.juniper.net/documentation/us/en/software/junos/cli/topics/topic-map/configuration-groups-usage.html")

