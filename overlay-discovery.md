# Network Overlay Discovery

Distributed systems come in a large variety of types, but share a common concern; new peers require an entry point, some known server that allows them to access the network overlay.
In many network overlays, any peer that is already member can serve as a entry point for any new peer, and allow it to make acquaintance with the rest of the network. Probably all
network overlays can be enriched with this feature, if they do not have it already. The trouble is acquisition of any of the members that can serve as entry point, without already
having the location of any other such member. In other words, all network overlays have a bootstrapping problem. 

NOD reduces the problem of having many bootstrapping problems to a single bootstrapping problem; only NOD needs to be joined to get entry into any network overlay registered in NOD.
NOD-enabled peers use heuristics to provide joining peers with peers closer them.

# Architecture

NOD is organized as a hierarchical file-system, much like zookeeper, or DNS for that matter. At any level, it forms a geo-spatially organized, 'sharded' index of all nodes on that level.
At the root, all nodes are stored. Each NOD member only needs to remember a few of them; In line with the small-world principle, one remembers many that are close and fewer the
further away (in terms of network latency). Intermediate nodes typically perform an organizational role, reducing the total set of nodes on the higher level, to a subset of them
having some form of interest in the thing represented by the node. Actual network overlays are registered in the leafs (although that is not strictly necessary).

Members periodically monitor each other by exchanging network health information, from their perspective, but taking into account information shared with them. Whenever any member
is queried for the entry nodes of a particular path, it provides the requester with a subset of nodes, enriched with metadata, including expected latency. The set of nodes returned
is chosen (heuristically) in line with the small-world principle.

Besides estimated network distance / latency and liveness, we monitor peer integrity. This is to protect against a number of attacks that could happen on this network, or the networks
it provides access to.

### Possible attacks

- Returning an altered list of entry-points for a query
    - either to trick a particular peer
    - or to scam peers indiscriminately
- Depending on the name-reservation-method:
    - Acquire a majority of peers for the name and overtake it

# Requirements

Any NOD peer is allowed to be a peer for the root node. Allowing constraints for lower-level nodes is likely useful. We should protect users against their network overlay being taken
over, but simultaneously, not make it so strong that a malevolent node 'owner' cannot be cleared of his property. Important that base functionality should be free of charge. Enforcement
of a particular constraint may have to come at a cost to prevent combined DDOS and sybil attacks.

# Problems

- Monetization
- Trademarks


## Features:

- Extremely lightweight: A bare version should run on a router, a version with more features enabled should run on an ordinary NAS or cheap smartphone.
- Implementation agnostic (any network overlay that publishes some entry points into NOD can be discovered and joined)
- Finding closest peers of a network overlay is cheap.
- Network monitoring and metrics

## Advantages:

- Probably more resilient than DNS->server in terms of surviving massive outages

## Disadvantages:

- Probably less resilient than DNS in terms of spoofability of nodes