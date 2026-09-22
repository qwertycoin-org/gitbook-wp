---
description: Implemented features, public-test classification and non-features
---

# Implementation and release status

This publication targets Qwertycoin Core `v2.0.2` and the QWC v2 network
profile identified in [Network history and the v2 reset](history.md).

| Baseline | Value |
| --- | --- |
| Core tag | `v2.0.2` |
| Core source commit | `54308d8473dc5606d054c0ba428cfb2d64e758c1` |
| Whitepaper update date | 22 September 2026 |

## Implemented protocol

| Area | Current status |
| --- | --- |
| Block production and chain selection | RandomX proof of work |
| Transaction privacy baseline | Monero-HF16-derived rules with CLSAG, RingCT, Bulletproof+ and view tags |
| QWC protocol | Hardfork version 17 from genesis |
| EPoSE format | Protocol version 2 only on the public v2 chain |
| Service lifecycle | Registration, renewal, update, deregistration and key recovery |
| Admission | Epoch-scoped 18-bit RandomX proof |
| Qualification | Frozen snapshots, three rounds, dynamic 2/3 quorum |
| Reward | 10% of scheduled subsidy, paid from the prior epoch's closed set |
| Reorg handling | Atomic state, undo and canonical replay |
| Public-test clients | Core/CLI, GUI and web-facing services |

## Release classification

`v2.0.2` is the stable-named client baseline published for **public testing**.
Project testing authorizes that public-test publication without claiming that
the independent EPoSE readiness gates have passed.

The EPoSE stable-readiness ledger remains `NO-GO (0/13)`. That status means the
required candidate-bound independent review and evidence set is incomplete. It
does not disable compiled HF17/EPoSE behavior at runtime, and it must not be
rewritten as an audit or security approval.

## Not part of Qwertycoin v2

The following ideas appeared in older whitepaper drafts but are not active v2
consensus features:

- EPoW consistency rewards or CryptoNight mining;
- proof of stake, staking pensions or a PoW-to-PoS transition;
- sharding or a Genesis Reference Block pruning scheme;
- a 10% governance fee, treasury output or on-chain project voting;
- native on-chain exchange, DeFi or NFT protocols;
- consensus-level FATF identity or address classification;
- collateral-backed master nodes or slashing.

Their removal from the current table of contents prevents research proposals
from being mistaken for implemented behavior. Repository history preserves
the earlier text.

## Compatibility rule

This whitepaper is explanatory. Exact behavior is defined by the release-
matched Core source, compiled consensus profile and canonical chain. Future
consensus changes require explicit versioning and updated documentation.
