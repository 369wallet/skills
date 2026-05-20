---
name: transfer-skill
description: Send native and ERC-20 tokens on Arc, Giwa, or BNB with sane gas defaults.
chains: [arc, giwa, bnb]
---

# transfer-skill

Move native assets or ERC-20 tokens between addresses. Picks reasonable gas parameters per chain and waits for confirmation by default.

## When to use

- Paying a counterparty.
- Funding a sub-account or session wallet.
- Sweeping balances out of a deprecated address.

## Capabilities

- `transfer(chain, asset, to, amount)` — execute a transfer.
- `estimateGas(chain, asset, to, amount)` — preview cost.
- `transferBatch(chain, items[])` — multiple transfers in a single transaction where supported.

## Inputs

- `chain`: `'arc' | 'giwa' | 'bnb'`
- `asset`: native sentinel or ERC-20 contract address.
- `to`: recipient address.
- `amount`: decimal amount string.

## Outputs

- Transaction hash, confirmation status, gas spent.
