---
description: Separation of proof of work, EPoSE state and application services
---

# Architecture

Qwertycoin v2 has one canonical blockchain and one chain-selection rule:
RandomX proof of work. EPoSE is an additional deterministic state machine that
is evaluated while each canonical block is connected or disconnected.

```text
transactions + bounded EPoSE records
                 |
                 v
         RandomX block candidate
                 |
                 v
 full-node validation and chain selection
        |                       |
        v                       v
 transaction state      deterministic EPoSE state
                                |
                                v
                   expected service reward plan
```

## Consensus layers

### Proof of work

Miners produce blocks and cumulative RandomX work chooses the canonical chain.
EPoSE cannot make a lower-work branch canonical.

### Transaction validation

Full nodes validate transaction structure, signatures, confidential-amount
proofs, fees, unlock rules and Coinbase issuance. The current chain begins at
QWC block version 17 and retains the Monero-HF16 transaction-rule baseline.

### EPoSE state

Blocks may carry bounded `QEP2` envelopes in the dedicated EPoSE transaction
extra field. Full nodes process lifecycle records, admission leases, service
receipts, qualification sets and reward commitments in canonical serialized
order. The resulting state commitment is stored atomically with the block.

If a branch is disconnected, recent EPoSE state is undone with the block. Deep
recovery replays canonical blocks and checks the stored commitments. Missing or
corrupt derived state fails closed; it cannot silently turn a required service
payment into a miner-only reward.

## Off-chain components

Endpoint discovery and live service challenges require networking, but
consensus validation itself performs no DNS lookup or network request. Signed
descriptors and receipts become relevant to consensus only after they are
included in the canonical chain.

Explorers, seed hosts, mining pools, node maps, DNS records and monitoring
systems are operational tools. They cannot change block validity.

## Bootstrap seeds are not privileged

The seed hosts compiled into Core help a new daemon find peers. EPoSE discovery
endpoints help participants exchange signed service descriptors. Neither list
is an EPoSE allowlist, and neither gives admission, committee, qualification or
reward priority. A QWC-operated seed must satisfy the same EPoSE rules as any
other service identity.
