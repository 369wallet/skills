---
name: multichain-signing
description: Unified transaction signing across Arc, Giwa, and BNB with chain-aware encoding and gas defaults.
chains: [arc, giwa, bnb]
---

# multichain-signing

Sign and broadcast EVM transactions on Arc, Giwa, or BNB through a single interface. Handles chain ID selection, gas conventions, and nonce management transparently.

## When to use

- Building agents that operate across more than one of {Arc, Giwa, BNB}.
- Abstracting away per-chain RPC and signing differences.

## Capabilities

- `sign(chain, tx)` — sign a transaction for the named chain.
- `broadcast(chain, signedTx)` — submit the signed transaction.
- `signAndSend(chain, tx)` — convenience combo.
- `getChainInfo(chain)` — chain ID, native asset symbol, RPC endpoint.

## Inputs

- `chain`: `'arc' | 'giwa' | 'bnb'`
- `tx`: EIP-1559 transaction object.

## Outputs

- Signed transaction hex, broadcast hash, confirmation receipt.

## Notes

- All three chains are EVM-compatible; encoding follows EIP-1559.
- Nonce is fetched from RPC unless explicitly provided.
