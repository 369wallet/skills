---
name: agent-wallet
description: Scoped, revocable session-key signing for autonomous agents on Arc, Giwa, and BNB.
chains: [arc, giwa, bnb]
---

# agent-wallet

Provision a session-scoped signing key for an agent with explicit capability and expiry constraints. The user's primary key never leaves the wallet; the session key can be revoked at any time.

## When to use

- Granting an agent permission to act for a bounded scope (chain, contracts, spend cap, duration).
- Rotating or revoking agent permissions without touching the master key.
- Auditing what an agent signed under a specific session.

## Capabilities

- `createSession(scope)` — issue a new session key.
- `revokeSession(sessionId)` — invalidate immediately.
- `signWithSession(sessionId, tx)` — sign within the session's scope.
- `listSessions(owner)` — enumerate active sessions for an owner.

## Inputs

- `scope`: `{ chain, contracts[], maxValue, expiresAt }`
- `tx`: EIP-1559 transaction object.

## Outputs

- Session metadata, signed transaction hex, broadcast tx hash.

## Notes

- Scope is enforced wallet-side before signing. Out-of-scope transactions are rejected, not forwarded.
- See [`resources/`](./resources) for the capability schema.
