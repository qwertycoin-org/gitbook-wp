---
description: Official public services and their relationship to consensus
---

# Public ecosystem

Qwertycoin's public services expose different views of the same network. They
are useful interfaces, but none replaces validation by a full node.

## Website and releases

[qwertycoin.org](https://qwertycoin.org/) publishes project information and
official download links. Stable update metadata is also published as DNSSEC-
validated TXT records under `updates.qwertycoin.org`; clients must still
verify release manifests and checksums rather than trust a filename alone.

## Explorer

[explorer.qwertycoin.org](https://explorer.qwertycoin.org/) displays canonical
blocks, transactions and chain statistics. Alternative or orphaned blocks may
be known to a daemon or pool without appearing as canonical explorer pages.
Explorer indexing cannot decide consensus.

## Web Wallet

[wallet.qwertycoin.org](https://wallet.qwertycoin.org/) provides browser-based
wallet operations, including exact-message signing and verification. Its
gateway exposes a constrained RPC surface; administrative daemon RPC is not a
public wallet API.

## Mining pool

[pool.qwertycoin.org](https://pool.qwertycoin.org/) is an optional PPLNS
service for RandomX miners. Pool fees, payout thresholds and schedules are
application policy and may change independently of consensus. The current
values are published by the pool API and interface. A pool-reported block
earns a reward only if it remains in the canonical chain.

## Node map

[nodes.qwertycoin.org](https://nodes.qwertycoin.org/) shows geospatially
aggregated **observed public peer IPs** over 24-hour, 7-day and 30-day windows.
It stores privacy-preserving keyed tokens for time-window deduplication rather
than raw IP history and publishes rounded aggregate locations.

One IP is not necessarily one node or operator, and one observing daemon does
not see the entire network. The map is operational telemetry, not an EPoSE
membership or reward registry.

## Trust boundary

Applications can be delayed, unavailable, misconfigured or disagree with a
node. Consensus-relevant decisions—block acceptance, transaction validity,
EPoSE state and rewards—come from version-matched Core validation against the
canonical chain.
