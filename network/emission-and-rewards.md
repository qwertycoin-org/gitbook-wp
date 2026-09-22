---
description: Monetary units, emission curve and allocation boundaries
---

# Emission and block rewards

Qwertycoin uses eight decimal places. One QWC equals `100,000,000` atomic
units.

## Monetary parameters

| Parameter | Value |
| --- | ---: |
| Emission-curve constant | 184,467,440.73709551 QWC |
| Emission speed factor per minute | 20 |
| Target block time | 120 seconds |
| Minimum subsidy | 0.6 QWC per block |
| Coinbase maturity | 60 blocks |

At the two-minute target, the unpenalized scheduled subsidy follows:

```text
max((emission_constant - already_generated) >> 19, 0.6 QWC)
```

Block-weight rules may reduce the actual subsidy for an oversized block. The
0.6-QWC minimum subsidy continues after the main emission curve, so QWC does
not have a strict final-supply cap. Tail emission provides a continuing mining
incentive.

## Allocation

Before the first EPoSE payout, the miner receives all scheduled subsidy and
transaction fees. From the first eligible payout height onward:

- a qualified EPoSE payee receives 10% of scheduled subsidy;
- the miner receives the remaining 90% of scheduled subsidy;
- the miner receives 100% of transaction fees;
- if the source qualification set is empty, the miner receives the full
  scheduled subsidy and all fees.

The EPoSE split does not create extra coins. Every full node validates the total
Coinbase amount, recipient and scoped service-payment proof.

There is no active consensus-level governance fee, treasury output, staking
reward or pool-fee output. Fees charged by a mining pool or other service are
separate application policy.
