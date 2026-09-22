---
description: Current transaction privacy mechanisms and their limits
---

# Privacy and transactions

Qwertycoin v2 inherits the mature CryptoNote/Monero transaction model and uses
the HF16-era privacy baseline under QWC block version 17.

## Mechanisms

| Mechanism | Purpose |
| --- | --- |
| One-time output keys | Prevent a recipient's public address from appearing directly as a reusable output destination. |
| Ring signatures (CLSAG) | Hide the real spent output among a ring of plausible outputs. |
| RingCT | Hide transaction amounts while preserving verifiable balance. |
| Bulletproof+ | Prove confidential output amounts are in range without revealing them. |
| View tags | Reduce wallet scanning work without granting spend authority. |
| Dandelion++ relay | Reduce simple network-layer linkage between transaction origin and first broadcast. |

The active minimum mixin is 15, corresponding to a ring of 16 members. The
wallet selects decoys according to the current implementation; users and
services should not construct nonstandard rings manually.

## Keys

A primary QWC address encodes public spend and view keys. The private spend key
authorizes spending and message signatures. The private view key lets a wallet
detect incoming outputs. Watch-only wallets can observe with view authority but
cannot spend or produce a spend-key ownership signature.

EPoSE is separate: its operator and online service keys authorize service-node
records only. They are not wallet keys and cannot spend service rewards.

## Privacy is a system property

Cryptography does not make every use anonymous. Address reuse, public mining
identities, exchange records, service-node endpoints, timing, network observers
and voluntary message signatures can create linkability. Users must evaluate
the complete operational context.

The protocol does not claim immunity from global traffic analysis, compromised
endpoints, malicious wallets or disclosure by third-party services. Always
verify wallet software and keep private keys offline from public services.
