---
name: swap-skill
description: Quote and execute token swaps on Arc, Giwa, or BNB through chain-native DEX routing.
chains: [arc, giwa, bnb]
---

# swap-skill

Fetch a swap quote and execute it on the requested chain. Supports exact-in and exact-out modes with slippage controls.

## When to use

- Agent needs to exchange one token for another.
- Portfolio rebalancing or fee-token preparation before another action.

## Capabilities

- `quote(chain, tokenIn, tokenOut, amount, mode)` — fetch a price.
- `execute(quote)` — submit the swap.
- `simulate(quote)` — dry-run estimate.

## Inputs

- `chain`: `'arc' | 'giwa' | 'bnb'`
- `tokenIn`, `tokenOut`: token addresses (use native sentinel for native asset).
- `amount`: decimal amount string.
- `mode`: `'exactIn' | 'exactOut'`.
- Optional: `slippageBps`, `recipient`, `deadline`.

## Outputs

- Quote object (`price`, `route`, `gasEstimate`), tx hash, executed `amountIn` / `amountOut`.

## Notes

- Routing is chain-native — Arc uses Circle-listed venues, Giwa uses Upbit ecosystem venues, BNB uses BNB Chain DEXes.
