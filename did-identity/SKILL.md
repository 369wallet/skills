---
name: did-identity
description: Issue and resolve portable on-chain DIDs across Arc, Giwa, and BNB with ECDSA signature proofs.
chains: [arc, giwa, bnb]
---

# did-identity

Register an agent's verifiable identity on-chain — name, capabilities, signing key — and resolve it from any of the three supported chains. The DID is portable: one identity is recognized across Arc · Giwa · BNB.

## When to use

- Establishing agent identity for reputation, capability discovery, or access control.
- Cross-chain agent interaction where one identity must be recognized everywhere.
- Proving an agent's authority via ECDSA challenge/response.

## Capabilities

- `register(profile)` — create a new DID document.
- `resolve(did)` — fetch the DID document from any supported chain.
- `proveOwnership(did, challenge)` — emit an ECDSA proof.
- `verifyProof(did, challenge, proof)` — validate a proof.
- `update(did, profile)` — modify capabilities or rotate key.

## Inputs

- `profile`: `{ name, capabilities[], publicKey, metadata }`
- `did`: DID URI string.

## Outputs

- DID document, registration tx hash, ECDSA proof bytes.

## Notes

- Documents are written on the chain you register from; resolution mirrors across the other two.
- See [`resources/`](./resources) for the DID document schema.
