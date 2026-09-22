---
description: Qwertycoin v2 technical whitepaper — updated 2026-09-22
---

# Qwertycoin v2 Whitepaper

Qwertycoin (QWC) is a privacy-preserving digital currency secured by
**RandomX proof of work**. Qwertycoin v2 adds **Egalitarian Proof of Service
(EPoSE) v2**, a deterministic protocol that qualifies service identities and
assigns part of the scheduled block subsidy without replacing proof of work.

RandomX remains the only block-production and chain-selection mechanism.
EPoSE does not use stake, collateral, delegated voting, or a second chain.

{% hint style="warning" %}
This whitepaper explains the current implementation. Consensus is defined by
the Qwertycoin Core source and the canonical chain. If prose and code disagree,
the implementation at the referenced release is authoritative.
{% endhint %}

## Current baseline

| Item | Current value |
| --- | --- |
| Core release | `v2.0.2` |
| Release classification | Stable client for public testing |
| Block version | QWC hardfork `17` from genesis |
| Mining consensus | RandomX (`rx/0`) proof of work |
| Service protocol | EPoSE protocol version `2` |
| Block target | 120 seconds |
| Display precision | 8 decimal places |
| EPoSE service share | 10% of scheduled subsidy; fees remain with the miner |

The current EPoSE evidence ledger remains `NO-GO` for stable/audit readiness.
That ledger is a release-assurance status, not a runtime switch. The v2.0.2
client and EPoSE protocol are available for public testing while independent
review and remaining evidence work continue.

## Official resources

- Website: [qwertycoin.org](https://qwertycoin.org/)
- Core source and releases:
  [github.com/qwertycoin-org/qwertycoin](https://github.com/qwertycoin-org/qwertycoin)
- Desktop wallet:
  [github.com/qwertycoin-org/qwertycoin-gui](https://github.com/qwertycoin-org/qwertycoin-gui)
- Web wallet: [wallet.qwertycoin.org](https://wallet.qwertycoin.org/)
- Explorer: [explorer.qwertycoin.org](https://explorer.qwertycoin.org/)
- Node map: [nodes.qwertycoin.org](https://nodes.qwertycoin.org/)
- Mining pool: [pool.qwertycoin.org](https://pool.qwertycoin.org/)

Continue with the [Introduction](introduction.md), or use the table of contents
to read a specific protocol section.
