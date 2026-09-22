---
description: Wallet types, safe message signing and ownership proofs
---

# Wallets and message signing

Qwertycoin provides native command-line and desktop wallets plus a browser
wallet. A wallet owns funds through its private spend key and discovers outputs
through its private view key. Node or EPoSE identity keys are separate and
cannot authorize wallet spending.

## Wallet safety

- A mnemonic seed or private key should be entered only into a trusted wallet,
  never a pool, explorer, support form or message.
- A watch-only wallet can observe compatible outputs but cannot create a valid
  spend-key ownership signature.
- Wallet caches can be rebuilt; seeds and keys cannot.
- Verify release checksums and provenance before installing native binaries.
- Treat browser storage as part of the local threat model and lock or close an
  unlocked wallet when finished.

## Message signing

The QWC wallets can sign an exact byte sequence with the address's spend-key
identity and verify a signature without exposing the private key. Message
signing does not create a transaction, move funds or grant general access to a
wallet.

Verification is byte-exact. Line endings, whitespace, domain, address, amount,
nonce or expiry changes produce a different message and must fail.

## Pool threshold requests

The official pool uses signed, short-lived challenges when a miner changes an
address-specific payout threshold. The challenge binds at least the action,
pool domain, QWC address, requested value, one-time nonce and expiry.

Safe flow:

1. obtain the challenge from the miner dashboard;
2. review the complete text and expiry;
3. sign that exact message in QWC GUI, CLI or Web Wallet;
4. submit only the resulting signature;
5. allow the pool to consume the nonce once.

The public address alone is not sufficient authority to change account
settings. The pool must reject altered, expired, replayed, wrong-domain and
wrong-address challenges. The wallet must never send a seed, private spend key
or wallet password to the pool.

Message signatures prove control of the signing key for the specific text.
They do not prove a real-world identity and should not be reused as a generic
login token.
