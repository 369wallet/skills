---
name: defi-adapters
description: Adapter slots for DeFi protocols on Arc, Giwa, and BNB. Plug lending, perps, and yield protocols in behind a common interface.
chains: [arc, giwa, bnb]
---

# defi-adapters

Registry and base interface for DeFi protocol adapters. Each adapter implements a small contract (`describe`, `quote`, `execute`) so an agent can discover and use a protocol without bespoke wiring.

## When to use

- Adding a new DeFi protocol to the 369wallet skill surface.
- Letting an agent pick the best protocol for a given task at runtime.

## Capabilities

- `register(adapter)` — install an adapter implementation.
- `list(chain?, category?)` — discover available adapters.
- `describe(adapterId)` — fetch capabilities, supported actions, and required inputs.
- `invoke(adapterId, action, params)` — execute against an adapter.

## Inputs

- `adapterId`, `action` name, action-specific params.

## Outputs

- Adapter response (varies by protocol).

## Notes

- Adapter implementations live under [`resources/adapters/`](./resources). This skill defines the interface, not the protocols themselves.
- Contributions of new adapters are welcome — see [CONTRIBUTING.md](../CONTRIBUTING.md).
