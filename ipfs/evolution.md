# IPFS - Evolution

<<<<<<< HEAD
The IPFS project was born in 2013 by Juan Benet, he knew Git's data-linking structure and is useful across many data types–not just code. Juan recognized that combining this concept with the P2P file-sharing structure of BitTorrent would be powerful: functional, secure information sharing without centralized barriers. This could transform the world far beyond scientific datasets.
the IPFS whitepaper was published in july 2014 and it caught the attention of many enthusiastis people. the contributors worked night, weekends and initally for free because they believed in the positive impact that open networks like IPFS could have on the world. The next year IPFS team was growing to get a cowroking space in Seattle to implement and release the go-ipfs in April 2016. The improvements of 0.4.0 transitioned IPFS from an "exciting demo" to a genuinely useful tool for early adopters. IPFS has come a long way in the journey to building a faster, safer, and more open web to preserve and grow humanity's knowledge.
the main difference of evolution of the first release to the newest are the speed to add a file, to provide, to find and fetching files. In 2016 IPFS got the first release with a few things comparing now, in this case the most important diferences are: the security of files, the usability of IPFS and the control of the network system.
=======
The IPFS project was born in 2013 by Juan Benet,  Juan  known Git's data-linking structure is useful across many data types–not just code. Juan recognized that combining this concept with the P2P file-sharing structure of BitTorrent would be powerful: functional, secure information sharing without centralized barriers. This could transform the world far beyond scientific datasets.

The IPFS whitepaper was published in july 2014 and it caught the attention of many enthusiastis people. The contributors worked nigth, weekends and initally for free because they believed in the positive impact that open networks like IPFS could have on the world. The next year IPFS team was growing to get a coworking space in Seattle to implement and release the go-ipfs in April 2016. The improvements of 0.4.0 transitioned IPFS from an "exciting demo" to a genuinely useful tool for early adopters. In 2018 IPFS entered the next phases of its maturation. The project need to deliver on its ideological ans technical advantages at scale. IPFS has come a long way in the journey to building a faster, safer, and more open web to preserve and grow humanity's knowledge.

The main difference in the evolution of the first release and the newest are the speed to adding a file, providing,  finding and fetching files. In 2016 IPFS got the first release with a few things comparing now, in this case the important improves are: the security of files, the usability of IPFS and the control of the network system.
>>>>>>> 0d5f9e365baf369fce9fd0e0dc6110e2b98bcc46

## Lines of code added and removed
Commits
![Commits](assets/commits.png)

Aditions
![Commits](assets/aditions.png)

Deletions
![Commits](assets/deletions.png)

Code Frequency
![Commits](assts/../assets/code_frec.png)




# ADR1: Implement QUIC - Release 0.4.18

## Context

- Sometimes TCP conections broke up when a file is transfering, intrerrupting the process.

## Decision

- Implement QUIC as a new protocol to solve issues with TCP.


## Status

- Implemented

## Consequences

- Fewer local resources: allow us to dial faster and keep more connections open.
- Faster connection establishment: significantly reduce the latency of DHT queries.
- Behaves better on lossy networks: QUIC handles multiplexing internally, dropping a single packets affects only the related stream.


# ADR2: Performance Resources - Release 0.4.18

## Context

<<<<<<< HEAD
- Currently the utilization of CPU and memory are too high because IPFS are consuming a lot of resources.
=======
- Actual the resource of utlization are a problem when it use the IPFS becouse the use a lot of CPU and memory.
>>>>>>> 0d5f9e365baf369fce9fd0e0dc6110e2b98bcc46

## Decision

- Changed two of the most frequently used datastructures, CIDs(unique ID for eachj file) and Multiaddrs(format for enconde addresses), to reduce allocation load.
- Store CIDs encode as strings, instead of decoded in structs.
- Changed many of our multiaddr parsing/processing/formatting functions to allocate less.


## Status

- Implemented

## Consequences

- Reduce CPU utilization when heavily using the DHT.
- Improve memory usage when inserting CID.



# ADR3: New DHT - Release 0.5.0

## Context

- DHT(Distributed hash table) is how IPFS nodes keep track of who has what data.
- The actual DHT implemented, have problems trying to connect to peers that cannot be reached wasting query time.
- The logic of DHT query doesn't properly terminate when it hits the end of the query, trying always to reconnect.
- The routing table are poorly maintened
  
## Decision

- Dual DHT
  - All IPFS nodes will now run two DHTs: one for the public internet WAN, and one for their local network LAN.

- Query Logic
  - Publishing IPNS & provider records.
  - Resolving IPNS addresses.
- Routing Tables
  - Addresing the poorly maintained routing tables by:

  - Reducing the probability that the connection manager will kill connections to peers in the routing table.
  - Keeping peers in the routing table even if we get disconnected from them.
  - Prioritizing useful peers that respond to queries fast.
## Status

- Implemented

## Consequences


- Connections terminate when hits the end of the query.
- Improve tables logic.
- Brings stability to connections.
- A lot of cost wasted rewriting the most of the module DHT.

# ADR4: QUIC by default - Release 0.6.0

## Context

- Currently, connections time is too slowly, so when it takes too long, TCP protocol quit the connection try.


## Decision

- QUIC transport is enabled by default for both inbound and outbound connections. When connecting to new peers, libp2p will continue to dial all advertised addresses in parallel (tcp + quic), so if the QUIC connection fails, the connection should still succeed.
- With the QUIC transport, the IPFS handshake takes two round trips. In the future, this will be improved for reduce it to one round trip.
- The QUIC transport will open one UDP socket per listen address instead of one socket per connection.
  

## Status

- Implemented

## Consequences

- Have to make two round trips for establish a connection and the handshake, this should be improved to one round trip. 

# ADR5: Removing support for the SECIO security transport - Release 0.7.0

## Context

- SECIO is a TLS-like security transport and has been the main security transport for all libp2p implementations. The problem is now browsers are introducing support for TLS1.3 and not all libp2p implementation can make it the default security transport.


## Decision

- Implement [Noise security transport](https://github.com/libp2p/specs/tree/master/noise) as the main security transport method.


## Status

- Implemented

## Consequences

- Older nodes on the network that only support SECIO will no longer be able to communicate with IPFS nodes after 0.7
