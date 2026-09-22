---
description: Service identity, endpoint lifecycle and epoch-scoped admission
---

# Identity, lifecycle and admission

## Identity separation

An EPoSE identity is derived from an offline operator-authorization public key
and bound to the network, genesis hash and parameter-set hash. It is not an IP
address, DNS name, reward address or online service key.

The signed lifecycle descriptor binds:

- the stable identity ID;
- a rotating online service public key;
- the offline operator-authorization public key;
- a primary public QWC reward address;
- the hash of a signed endpoint descriptor;
- a monotonically increasing sequence number;
- effective and expiry epochs.

Lifecycle transitions support registration, renewal, endpoint updates,
deregistration and service-key recovery. They are future-effective and must
reference the previous descriptor. Active identities cannot share an online
service key.

The EPoSE keystore contains operator and service keys only. It does not contain
wallet spend keys, wallet view keys or funds.

## Endpoint descriptors

Endpoint descriptors are signed discovery objects. They bind the current
online key, canonical transport, public host and port, service kind, version,
sequence and expiry epoch.

Accepted targets are canonical public IPv4, IPv6 or lowercase DNS names.
Loopback, private, link-local, multicast, unspecified, mapped and malformed
targets are rejected. A discovered descriptor matters only if its hash is
authorized by the canonical lifecycle state or frozen membership snapshot.

Hardcoded seed nodes and configured discovery sources are bootstrap aids, not
an allowlist. They confer no admission, committee, qualification or reward
advantage.

## Admission proof

Participation in target epoch `E` requires an epoch-scoped RandomX admission
lease. The proof binds the frozen identity, descriptor, target epoch, canonical
context block, nonce, work hash and lease hash.

The compiled target is **18 leading zero bits**. It is an anti-spam work floor,
not proof of stake and not a complete Sybil defense. The active-population cap
and verifier quorum are separate protections.

| Admission parameter | Value |
| --- | ---: |
| Leading-zero target | 18 bits |
| Maximum frozen population | 100 identities |
| Lease scope | Target epoch |
| Context | Start block of epoch `E - 1` |

For epoch length `720` and anchor depth `60`, admission and lifecycle records
for target epoch `E` must be included no later than:

```text
enrollment_cutoff(E) = epoch_start(E) - 61
```

Membership is frozen one block later at `epoch_start(E) - 60`, before records
in that anchor block are applied. A late registration, renewal, endpoint update
or admission lease cannot retroactively join the already frozen epoch.

Service-node enrollment is automatic in the v2 daemon when configured with a
valid identity, reward address and public restricted endpoint. It does not
construct a funded registration transaction and does not require a wallet
private key.
