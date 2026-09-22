---
description: Purpose, boundaries and lifecycle of EPoSE v2
---

# EPoSE v2 protocol overview

Egalitarian Proof of Service (EPoSE) v2 is Qwertycoin's deterministic service
qualification and reward layer. It lets the canonical chain recognize service
identities that repeatedly prove availability and assign them a bounded share
of future block subsidy.

EPoSE is **not** a block-production or chain-selection protocol. RandomX proof
of work remains solely responsible for both. EPoSE has no stake, collateral,
slashing, delegated voting, master-node lockup or secondary chain.

## Protocol pipeline

For each target service epoch, the implemented path is:

1. an operator creates or updates a signed service identity and public endpoint;
2. the node solves an epoch-scoped RandomX admission proof;
3. eligible identities are frozen into a canonical membership snapshot;
4. deterministic verifier committees probe each subject in three rounds;
5. subject and verifier signatures bind successful canonical-object checks;
6. receipts included in the canonical chain are counted at the evidence
   deadline;
7. identities passing at least two rounds enter the closed qualification set;
8. the following epoch deterministically rotates service rewards over that set.

Only records accepted in canonical blocks affect qualification or rewards.
Discovery responses, relay queues, local databases and operator configuration
are not consensus state.

## Implemented service

The current service kind is `canonical-object`. A selected verifier requests a
specific canonical block from the subject's restricted public interface. The
subject returns the block bytes and a signature. The verifier checks those
bytes against its own canonical chain view and signs a receipt that commits to
the subject response.

Consensus later validates the signed transcript. It never performs DNS
lookups, remote RPC calls or wall-clock checks while validating a block.

## Bounded design

The public v2 profile bounds all expensive work:

- at most 100 identities in a frozen membership snapshot;
- committees of at most 9 independent subject-excluding members;
- three fixed receipt rounds;
- admission-work, parsing, signature and record-count budgets;
- bounded relay queues and deterministic template selection.

Malformed, conflicting, over-budget or context-invalid records fail closed.
State application is atomic and reorgs restore or replay canonical state.

Continue with [Identity, lifecycle and admission](identity-and-admission.md).
