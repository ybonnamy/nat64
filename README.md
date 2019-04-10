## NAT64 on OpenWRT with separated IPv4 and IPv6 interfaces

please see original repository for nat64 explanations : [cvmiller/nat64](https://github.com/cvmiller/nat64)

script is updated to work with my configuration :

```

+-------------+              +--------------------------+
| Freebox     |-----  red----| IPfire - no IPv6 support |
|	      |              | "Production" IPv4 Only   |
+-------------+              +--------------------------+
    |                                     |
    |                                   green ------------------------------> VLAN1 - Operational Home Network
    |					  |
    |					  |
    |					 wan (IPv4 Only)
    |					  |
    |                        +--------------------------+
    |----- wan6 ( IPv6 Only)-|        OpenWRT           |-lan (IPv4 Only)--|
    			     |                          |                  |-> VLAN6 - Experimental Home Network
                             |     "Experimental"       |-lan6(IPv6 Only)--| 
                             +--------------------------+

```

### Why?

To experiment Dual Stack or IPv6 only configuration. Just stop/start OpenWRT lan/wan interfaces to suppress IPv4, and keep only lan6/wan6 interfaces. nat64 can be tested just with a stop of the OpenWRT lan interface





