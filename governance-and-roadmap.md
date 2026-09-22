---
description: Project decision process and conservative protocol roadmap
---

# Governance and roadmap

Qwertycoin v2 has no consensus treasury, governance fee or token-weighted
on-chain voting mechanism. Project governance occurs through public source
control, issues, pull requests, review, tests, signed releases and operator or
community adoption.

No maintainer decision can make an invalid block valid. Consensus changes must
be implemented in Core, explicitly versioned, tested against reorg and replay
behavior, documented and adopted by network participants.

## Roadmap principles

Future work should preserve these boundaries:

1. RandomX remains responsible for block production and chain selection unless
   a separately specified hardfork changes that rule.
2. EPoSE changes remain deterministic, resource-bounded and tied to canonical
   state.
3. Funds safety and wallet-key separation take priority over operational
   convenience.
4. Parameters are not changed by runtime flags or documentation alone.
5. Public claims distinguish implemented behavior, test evidence, independent
   review and proposals.
6. Application services remain separable from consensus.

## Current priorities

- complete candidate-bound EPoSE review and readiness evidence;
- expand adversarial, multi-node, reorg, resource and wallet-funds testing;
- improve RPC status semantics so pending current-epoch qualification and
  eligibility for current rewards are shown separately;
- measure operator and infrastructure diversity without turning network
  metadata into consensus identity;
- maintain reproducible multi-platform releases and provenance.

Any future privacy, scalability, governance or application proposal should be
published as a proposal until code, tests, activation rules and deployment
evidence exist. It should not be described as a current feature in this
whitepaper.
