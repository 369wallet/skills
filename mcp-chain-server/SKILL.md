---
name: mcp-chain-server
description: MCP server exposing read-only chain operations on Arc, Giwa, and BNB.
chains: [arc, giwa, bnb]
---

# mcp-chain-server

A Model Context Protocol server for raw chain reads — block height, transaction lookup, log queries, contract calls — across Arc, Giwa, and BNB. Pairs with [`mcp-wallet-server`](../mcp-wallet-server) for write paths.

## When to use

- Agents that need to inspect chain state before acting.
- Indexing or observability workflows.
- Sanity checks (confirmations, log matching) inside larger flows.

## Tools exposed

- `chain.getBlock`
- `chain.getTransaction`
- `chain.getLogs`
- `chain.call`
- `chain.estimateGas`

## Inputs

- Chain selector + RPC-shaped parameters.

## Outputs

- JSON results matching standard EVM RPC schemas.

## Notes

- Read-only by design. All mutations go through [`mcp-wallet-server`](../mcp-wallet-server).
