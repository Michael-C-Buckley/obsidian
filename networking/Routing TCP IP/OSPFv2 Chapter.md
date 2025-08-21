

RFCs mentioned:
* 1131 - Version 1
* 1246 - Version 2
* 2328 - Version 3


# Neighbors and Adjanceny

### Hello Info

* Router ID
* Area ID of interface
* Address mask of interface
* Auth type and info
* Hello interval
* Dead interval
* Priority
* DR/BDR
* Five flags of optional capabilties
* RIDs of neighbors


## Network Types

* Point-to-Point
* Broadcast
* Nonbroadcast Multi-access (NBMA)
* Point-to-Multipoint
* Virtual Link

## Designated Routers

Priority is an 8-bit value

New routers coming onto a segment will set `0.0.0.0` for the DR and BDR

#### Election
1. 


### Point-to-Multipoint

Special subset of NBMA where the networks are treated as a collection of P2P links.

### Virtual Links

Present as unnumbered P2P links, packets are sent unicast between peers.


### General Network Types

* Transit
* Stub

Not to be confused with OSPF network types.  These are general designs.  Transit have 2 or more routers.  Stub has only 1 router.

### Facts:

* Supported TOS but never widely implemented (2328 deleted it)
* LSAs are retransmitted every 30 minutes

## Areas

* 32-bit (expressed either dot-demical or integer)
* Traffic types
	* Intra-area
	* Inter-area
	* External
* Area 0 (0.0.0.0) is reserved for the backbone
* Designers typically limit routers between 30-200 per area

### Partitioned Areas

Created when a link failure breaks pathing within or between areas.


## Link-State Database

* LSAs have a max age of 1 hour
* LSRefresh happens every 30 minutes

### LSRefresh

Sent out every 30 minutes to refresh existing LSAs and reset their timer.
Sequence number is incremented by 1.

Older Cisco platforms used to update all LSAs together, which introduced problems.
*Group Pacing* was  introduced to stop the spiking of CPU by grouping them.
Cisco uses 4 minute timers by default.


## LSAs

| Type  | Description          |     |
| ----- | -------------------- | --- |
| 1     | Router               |     |
| 2     | Network              |     |
| 3     | Network Summary      |     |
| 4     | ASBR Summary         |     |
| 5     | AS External          |     |
| ~~6~~ | ~~Group Membership~~ |     |
| 7     | NSSA External        |     |
| 8     | External Attributes  |     |
| 9     | Opaque (Link-Local)  |     |
| 10    | Opaque (Area Local)  |     |
| 11    | Opaque (AS Scope)    |     |

