---
name: balance-portfolio
description: Query native and token balances across Arc, Giwa, and BNB and aggregate them into a portfolio view.
chains: [arc, giwa, bnb]
---

# balance-portfolio

Read on-chain balances per address — native and known ERC-20s — and aggregate them into a single portfolio object across the supported chains.

## When to use

- Before swap/stake/transfer to verify funds.
- Building dashboards or status replies for agents.
- Computing total exposure across chains.

## Capabilities

- `getBalance(chain, address, asset?)` — single-chain balance.
- `getPortfolio(address, chains?)` — aggregate across supported chains.
- `getTokenList(chain)` — known token registry per chain.

## Inputs

- `address`, optional `chain` and `asset` filters.

## Outputs

- Per-chain balance map and aggregated portfolio summary with USD-equivalent totals.
