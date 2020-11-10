# IPFS - Evolution

the main difference of evolution of v0.2.2 to 0.7.0 are 3, in 2015 IPFS got the first release that hD a few things comparing now, in this case the mos important diferednces are: 

the security of files: in the first version ipfs that not have yet nay kind of securty but today in the current version they have a security system and also they dont done this improvement.

the usability of IPFS: in the first version only have the usage of comand line, now in  the last version have alot of usage IPFS and have many iteraccion with alot of services, this help to use the IPFS as a single user, for example, the ipfs Desktop, cluster, jsipfs, etc.

the control of the network system: in the first version, thay not have thee 3 protocol that have today and the control for user in the network for example, manage the peers.

## Lines of code added and removed
Commits
![Commits](assets/commits.png)

Aditions
![Commits](assets/aditions.png)

Deletions
![Commits](assets/deletions.png)



# ADR


# New DHT - Release 0.5.0

## Context

- Actual DHT have problems trying to connect to peers that cannot be reached wasting query time.
- The logic of DHT query doesn't properly terminate when it hits the end of the query, trying always to reconnect.
- The routing table are poorly maintened
  
## Decision

- Dual DHT
  - All IPFS nodes will now run two DHTs: one for the public internet WAN, and one for their local network LAN.

- Query Logic
  - Improove the DHT query logic to more closely follow Kademlia. This should significantly speed up:
    - Publishing IPNS & provider records.
    - Resolving IPNS addresses.
- Routing Tables
  - Addresing the poorly maintained routing tables by:

  - Reducing the likelihood that the connection manager will kill connections to peers in the routing table.
  - Keeping peers in the routing table, even if we get disconnected from them.
  - Actively and frequently querying the DHT to keep our routing table full.
  - Prioritizing useful peers that respond to queries quickly.
## Status

Verified

## Consequences

A lot of cost wasted rewriting the most of the module DHT

# QUIC by default - Release 0.6.0

## Context

- QUIC transport is enabled by default for both inbound and outbound connections. When connecting to new peers, libp2p will continue to dial all advertised addresses in parallel (tcp + quic), so if the QUIC connection fails, the connection should still succeed.

## Decision

- With the QUIC transport, the IPFS handshake takes two round trips. In the future, this will be improved for reduce it to one round trip.
- The QUIC transport will open one UDP socket per listen address instead of one socket per connection.
  

## Status

Implemented

## Consequences

- Have to make two round trips for establish a connection and the handshake, this should be improved to one round trip. 

# Removing support for the SECIO security transport - Release 0.7.0

## Context

SECIO is a TLS-like security transport and has been the main security transport for all libp2p implementations. The problem is now browsers are introducing support for TLS1.3 and not all libp2p implementation can make it the default security transport.


## Decision

- Implement [Noise security transport](https://github.com/libp2p/specs/tree/master/noise) as the main security transport method.


## Status

Deprecated

## Consequences

- Older nodes on the network that only support SECIO will no longer be able to communicate with IPFS nodes after 0.7




4.18
change type of CID
implement quic 
4.19
-