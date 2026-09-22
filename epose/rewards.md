---
description: Deterministic EPoSE reward selection and Coinbase validation
---

# Service rewards

## Source epoch

A block in payout epoch `E` uses only the finalized qualification set from
source epoch `E - 1`. Records in the payout block or evolving current epoch
cannot change its payee.

The first service epoch is `1`; the first possible payout is at height `1440`,
the beginning of epoch `2`.

## Payee selection

Qualified service public keys are canonically ordered. Selection is bound to
the qualification commitment, network, genesis, parameter set, payout epoch
and canonical payout seed. Block position then rotates deterministically over
the qualified set.

Every validating node with the same canonical chain derives the same payee.
Being a hardcoded seed, discovery source, mining pool or project-operated host
provides no special position in that rotation.

## Allocation

When a qualified payee exists:

```text
service_subsidy = floor(scheduled_subsidy * 10%)
miner_subsidy   = scheduled_subsidy - service_subsidy
miner_fees      = all transaction fees
```

If the source qualification set is empty, the miner receives the entire
scheduled subsidy and all transaction fees. No extra coins are created and
there is no consensus governance or treasury output.

## Standard wallet outputs

The service reward address is a normal primary QWC address. Coinbase creates
ordinary CryptoNote one-time outputs using its transaction key and the
address's public view and spend keys. Wallet private keys never enter
registration, node configuration or consensus validation.

The service amount is decomposed with normal denomination rules and becomes
spendable after the normal 60-block Coinbase maturity.

## Scoped payment proof

When a service payment is required, Coinbase contains one scoped service
payment proof. It commits to the chain profile, height and parent, source
qualification set, selected identity and reward address, exact amount,
Coinbase transaction public key, claimed output indexes and canonical Coinbase
bytes.

Every full node reconstructs the reward plan before accepting the block. A
missing or extra proof, wrong payee, incorrect amount, duplicate output,
underpayment, overpayment or transplanted proof invalidates the block.
