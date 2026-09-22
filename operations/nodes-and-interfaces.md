---
description: Node roles, network ports, RPC boundaries and safe deployment
---

# Nodes, interfaces and safe exposure

## Node roles

A normal full node validates RandomX blocks, transactions and all EPoSE state
transitions. A mining node additionally creates block templates. A configured
EPoSE service node also maintains a service identity, solves admission work,
serves the restricted canonical-object endpoint and performs assigned probes.

No special node can override normal block validation or chain selection.

## Default ports

| Interface | Default TCP port | Intended exposure |
| --- | ---: | --- |
| P2P | `8196` | Public when accepting peers |
| Daemon RPC | `8197` | Loopback or a strictly controlled gateway |
| EPoSE restricted probe RPC | `8198` | Public for admitted service nodes |
| ZMQ | `8199` | Local/trusted consumers only |

The unrestricted daemon RPC exposes administrative and relay surfaces and
must not be placed directly on the public Internet. Public applications should
use a narrow method allowlist, request-size limits, connection limits and
rate-limiting in front of a fixed internal RPC address.

The EPoSE endpoint is deliberately restricted. Its descriptor must advertise a
canonical public target that other committee members can reach. A configured
service node should retain the complete canonical block data needed to answer
canonical-object probes; pruning that removes required objects is unsuitable.

## Bootstrap and discovery

Compiled seed nodes help a new daemon discover P2P peers. EPoSE discovery
sources help locate signed endpoint descriptors. Neither list grants
membership or rewards. Admission, frozen membership, receipts and canonical
qualification are still required.

## Operational boundaries

- Keep the unrestricted RPC on loopback or a private container network.
- Expose only the restricted service interface required by EPoSE.
- Separate application gateways, wallets and databases from the daemon.
- Use non-root containers, read-only root filesystems and explicit volumes
  where practical.
- Back up identity and wallet material separately; they have different trust
  and recovery properties.
- Monitor chain height, genesis, peer connectivity, endpoint reachability and
  qualification evidence rather than process liveness alone.

Explorer, node-map and pool services are observers or applications. Their
databases and status labels are not consensus state and cannot make a block or
service identity canonical.

For exact daemon options and RPC schemas, use the version-matched Core
documentation linked in [References](../references.md).
