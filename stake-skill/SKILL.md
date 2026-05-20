---
name: stake-skill
description: Deposit, claim, and unstake on Arc, Giwa, and BNB staking protocols through a unified interface.
chains: [arc, giwa, bnb]
---

# stake-skill

Manage staking positions across supported chains. Wraps protocol-specific deposit, reward claim, and unstake flows behind a unified surface.

## When to use

- Putting idle assets to work.
- Claiming rewards on a schedule.
- Unwinding positions safely with cooldown awareness.

## Capabilities

- `stake(chain, protocol, amount)`
- `claim(chain, protocol, positionId)`
- `unstake(chain, protocol, positionId, amount)`
- `getPositions(chain, address)`
- `getApr(chain, protocol)`

## Inputs

- `chain`, `protocol` identifier, `amount`, `positionId`, `address`.

## Outputs

- Transaction hashes, position state (`principal`, `rewards`, `unlocksAt`).

## Notes

- Supported protocols per chain are listed in [`resources/protocols.json`](./resources).
