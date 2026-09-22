---
description: Relationship between historical Qwertycoin and the current v2 network
---

# Network history and the v2 reset

Qwertycoin began in 2018. Earlier whitepaper revisions described many proposed
systems—including EPoW reward formulas, proof of stake, sharding, a governance
fee, on-chain voting, DeFi transactions and NFTs. Those documents mixed
implemented behavior with research ideas and future plans.

The current v2 network deliberately replaces that specification with a smaller,
verifiable protocol:

- RandomX proof of work secures block production and chain selection;
- Monero-HF16 transaction rules form the retained privacy baseline;
- QWC hardfork version 17 and EPoSE protocol version 2 are active from height 0;
- EPoSE assigns service rewards but does not introduce proof of stake;
- consensus values are compiled and bound to the v2 genesis and parameter-set
  hashes.

## Fresh network identity

Qwertycoin v2 is a fresh network, not a continuation of the legacy chain
database. Old blockchain files, peer state, wallet cache files and historical
balances are not imported into the v2 canonical chain. Old key material may be
useful for address-recovery experiments, but it does not recreate an old-chain
balance on v2.

| Identifier | Value |
| --- | --- |
| Mainnet genesis hash | `4f95857586e2c66063c277370eda99cd75897d773af09f0c3cd1e22f7e87db39` |
| EPoSE parameter-set hash | `2c26755094535871dd3ede7bd1b50aba82a9fb6831f0a17f32968eb0385145c6` |
| QWC block version | `17` from height `0` |
| EPoSE protocol version | `2` |

The launch template creates no special governance or service-node premine.
Normal emission and validated Coinbase rules govern issuance.

## Treatment of legacy proposals

Unsupported legacy proposal pages were removed from the current publication so
they cannot be mistaken for live consensus. Git history preserves them for
research and attribution. [Implementation and release status](status.md)
lists the important proposals that are not part of Qwertycoin v2.
