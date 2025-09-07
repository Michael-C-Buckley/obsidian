JunOS requires a few different commands in order to create a LAG, and other chassis configs:

* Set interfaces to their mode and bind to an aggregator interface
* Set aggregated options on the aggregator interface
* Ensure the chassis has enough aggregator devices enabled

Example config:

```
interfaces {
    interface-range ae0-members {
        member ge-0/0/1;
        member ge-0/0/2;
        gigether-options {
            802.3ad ae0;
        }
    }
    ae0 {
        aggregated-ether-options {
            lacp {
                active;
            }
        }
    }
}
chassis {
    aggregated-devices {
        ethernet {
            device-count 1;
        }
    }
}
```
