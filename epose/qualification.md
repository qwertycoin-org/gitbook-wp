---
description: Epoch timing, verifier committees, receipts and qualification
---

# Epochs, committees and qualification

## Epoch timeline

With activation height `0`, epoch length `720` and anchor depth `60`:

```text
epoch_start(E)       = E * 720
epoch_end(E)         = epoch_start(E) + 719
enrollment_cutoff(E) = epoch_start(E) - 61
committee_anchor(E)  = epoch_start(E) - 60
evidence_deadline(E) = epoch_start(E) + 659
```

Epoch `0` is the activation epoch. Epoch `1` is the first service epoch. The
first possible service payout is at height `1440`, the start of epoch `2`.

At the committee anchor, Core freezes accepted leases and lifecycle
descriptors into a canonical membership snapshot. Later arrival order,
descriptor changes or admission work cannot change that snapshot.

## Deterministic committees

For every subject and round, all other frozen members are candidates. Core
scores them from the network, genesis, parameter set, snapshot, epoch, round,
round anchor, subject and candidate. The lowest scores form a committee of at
most nine members.

```text
actual_committee  = min(9, frozen_population - 1)
required_receipts = ceil(2 * actual_committee / 3)
```

The subject can never verify itself. Empty and one-member snapshots therefore
cannot qualify an identity.

Examples:

| Frozen identities | Committee per subject | Receipt quorum per round |
| ---: | ---: | ---: |
| 3 | 2 | 2 |
| 4 | 3 | 2 |
| 10 or more | 9 | 6 |

With four identities, a subject is checked by the other three and needs two
distinct valid receipts. With three identities, both other members must
provide valid receipts.

## Three receipt rounds

Rounds begin at offsets `0`, `200` and `400` from the service-epoch start. A
subject must reach the dynamic quorum in at least **two of three rounds**.

Each receipt binds the snapshot and round, selected subject and verifier,
endpoint descriptor, requested canonical object, signed subject response and
signed verifier decision. A receipt must be included in the canonical chain by
the inclusive evidence deadline. Relay alone is insufficient.

At the deadline, Core counts distinct verifier keys in each exact slot. Exact
authenticated duplicates are idempotent; conflicts and self-receipts are
invalid. The final qualified set is canonically ordered and committed for the
epoch.

## Interpreting node status

The current epoch's qualification set does not exist until its evidence
deadline. Consequently, a local `qualified` flag may be `false` for most of an
otherwise healthy epoch. At the two-minute target, the deadline occurs about
22 hours after the epoch begins.

Rewards during epoch `E` use the already closed set from epoch `E - 1`.
Therefore these are different questions:

- has this node finalized qualification for the still-running epoch?
- is it eligible for current rewards from the previous epoch?

A `false` current-epoch flag before the deadline normally means **pending**,
not failed. After the deadline it indicates a real miss, commonly caused by a
late lease, absence from the snapshot, an unreachable endpoint, divergent
chain view, insufficient receipts or evidence that was not included in time.
