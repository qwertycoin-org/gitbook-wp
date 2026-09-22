---
description: Security assumptions, enforced boundaries and residual risks
---

# Security model and limitations

EPoSE is a bounded availability-reward protocol layered on proof of work. Its
security goals are deterministic validation, authenticated service evidence,
bounded resource use and predictable failure. It does not claim to prove that
one key equals one person or operator.

## Enforced protections

- **Consensus separation:** RandomX alone selects the canonical chain.
- **Context binding:** identities, leases, snapshots, receipts and payments
  bind network, genesis and the compiled parameter set.
- **Independent signatures:** the subject signs the service response and the
  selected verifier signs the resulting receipt.
- **Frozen membership:** post-anchor changes cannot influence committees for
  an epoch already in progress.
- **Dynamic supermajority:** quorum is `ceil(2n/3)` of the committee that can
  actually be formed.
- **Temporal separation:** qualification in one epoch funds only the next.
- **Bounded parsing and work:** malformed, oversized or over-budget record sets
  fail before unbounded signature or RandomX work.
- **Fail-atomic state:** invalid blocks do not partially mutate EPoSE state;
  disconnect and replay follow canonical chain state.
- **Funds separation:** EPoSE operator/service keys are not wallet keys.

## Residual risks

### Sybil identities

The 18-bit RandomX admission proof is an anti-spam floor, not strong economic
identity. A well-resourced operator can control multiple admitted identities.
The 100-member cap limits resource exposure but does not establish operator
independence.

### Small-network collusion

Bootstrap committees are necessarily small. With four frozen identities, two
colluding verifier identities meet the 2-of-3 per-round quorum for a subject.
The security of a mature 6-of-9 committee must not be attributed to a
four-identity deployment.

### Correlated infrastructure

Different public keys can share one operator, provider, ASN, jurisdiction or
backend. Consensus intentionally does not infer operator diversity from
network metadata.

### Routing and censorship

DNS failure, targeted routing attacks, endpoint filtering, verifier
withholding or miners excluding evidence can prevent qualification. The
protocol authenticates evidence but cannot prove why expected evidence is
absent.

### Key compromise

Compromise of an online service key can impersonate the endpoint until a
future-effective recovery transition is accepted. The offline operator key is
therefore the recovery authority and should remain separated. Neither key can
spend the reward wallet.

### Reorganizations

Membership, receipts, qualification and rewards follow the canonical chain.
A reorganization before finalization may legitimately change them. Persisted
state is commitment-bound and replayed rather than silently falling back.

## Release assurance

Implementation does not by itself prove production readiness. Qwertycoin
tracks independent review, adversarial testing, multi-node rehearsals, wallet
funds safety, resource limits and platform builds as separate evidence gates.
The v2.0.2 client is a public-test release; its EPoSE stable-readiness ledger
remains `NO-GO (0/13)` and must not be described as completed audit evidence.
