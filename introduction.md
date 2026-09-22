---
description: Purpose, design principles and participant roles
---

# Introduction

Qwertycoin is an open-source peer-to-peer currency. Its current v2 network is
derived from the Monero 0.18.x/CryptoNote code family and uses QWC-specific
network identity, genesis, address prefixes, emission parameters and EPoSE
consensus extensions.

The project has four primary design goals:

1. **Permissionless block production.** Anyone can mine using the public
   RandomX proof-of-work rules.
2. **Private-by-default transactions.** The transaction layer combines
   one-time output addresses, ring signatures and confidential amounts.
3. **Deterministic service incentives.** EPoSE rewards qualified service
   identities through rules every full node can reconstruct from canonical
   chain data.
4. **User-controlled keys.** Wallet spend and view keys remain with the user;
   service-node identity keys cannot spend wallet funds.

## Participant roles

| Role | Responsibility |
| --- | --- |
| Miner | Builds RandomX blocks, orders transactions and extends the canonical chain. |
| Full node | Validates proof of work, transactions, EPoSE state and Coinbase rewards. |
| EPoSE service node | Publishes a signed endpoint, performs admission work, answers canonical-object challenges and participates in verification committees. |
| Wallet | Detects and spends outputs controlled by the user's keys and may sign messages as proof of address control. |
| Explorer, pool and node map | Application services that observe or help use the network; they are not consensus authorities. |

## What EPoSE is not

Despite the word “service,” EPoSE is not proof of stake. It does not grant
chain-selection power, does not require locking QWC, and does not let service
nodes replace miners. A valid block always requires RandomX proof of work and
must satisfy every normal transaction and reward rule.

The current service kind proves a bounded signed exchange of a canonical block
object. It does not prove one human per identity, dedicated hardware,
geographic independence, permanent uptime or a commercial service-level
agreement.

## Documentation boundary

This whitepaper describes public protocol behavior and public software. It does
not publish infrastructure inventories, origin addresses, administrative
routes, credentials, private monitoring topology or wallet secrets.

For operator commands and normative implementation details, use the
[EPoSE documentation in Qwertycoin Core v2.0.2](https://github.com/qwertycoin-org/qwertycoin/tree/v2.0.2/docs/epose).
