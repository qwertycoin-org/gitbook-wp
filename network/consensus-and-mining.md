---
description: RandomX proof of work and canonical-chain behavior
---

# RandomX mining and chain selection

Qwertycoin v2 uses RandomX (`rx/0`) proof of work. RandomX is designed around
general-purpose CPUs and a memory-hard virtual machine. Mining is permissionless:
the validity of a block depends on its proof, contents and parent state—not on
the miner's identity or pool.

## Core parameters

| Parameter | Value |
| --- | ---: |
| Target block interval | 120 seconds |
| Difficulty window | 720 blocks |
| Coinbase maturity | 60 blocks |
| Normal output spendable age | 10 blocks |
| Full-reward-zone floor | 300,000 bytes |

Difficulty adapts from chain data. A valid block must satisfy the current
difficulty, reference a valid parent and pass all transaction, EPoSE and
Coinbase checks. Cumulative proof of work determines the winning branch.

## Mining and EPoSE

Miners do not decide which service identity receives a reward. For each height,
Core derives the expected payee from the previously closed EPoSE qualification
set. A miner may choose which valid pending EPoSE records to include, but cannot
fabricate signatures or redirect a required service payment without producing
an invalid block.

Reserved relay and template capacity reduce accidental starvation of enrollment
and evidence records. They cannot force an adversarial miner to include a
record, so sustained mining censorship remains a protocol risk.

## Pools and alternative blocks

A mining pool is an application-layer coordinator. It distributes templates,
verifies shares and accounts for rewards, but it has no special consensus
authority.

Two miners may find valid blocks for the same parent at nearly the same time.
Only the branch with the winning cumulative work remains canonical. A valid
block on the losing branch becomes an alternative/orphan block and its Coinbase
is not spendable. This is normal proof-of-work behavior, not an explorer or
accounting decision.

The current official pool exposes live policy and accounting data through its
own API. Pool fees, PPLNS windows and payout thresholds are operator policy and
are not Qwertycoin consensus parameters.
