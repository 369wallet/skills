---
name: mcp-wallet-server
description: MCP server exposing 369wallet signing, identity, and asset operations as tools for any MCP client.
chains: [arc, giwa, bnb]
---

# mcp-wallet-server

A Model Context Protocol server that surfaces wallet operations as discoverable tools. Any MCP-compatible client — Claude, IDEs, agent frameworks — can list and invoke them.

## When to use

- Embedding 369wallet capabilities into an MCP-aware agent runtime.
- Letting an LLM-driven agent discover wallet tools at runtime instead of hard-coding them.

## Tools exposed

- `wallet.sign`
- `wallet.transfer`
- `wallet.swap`
- `wallet.stake`
- `wallet.balance`
- `did.resolve`
- `did.register`
- `x402.request`

## Inputs

- MCP tool invocations per the published schema (see [`resources/`](./resources)).

## Outputs

- Typed MCP tool responses.

## Notes

- Pair with [`mcp-chain-server`](../mcp-chain-server) when read-only chain access is also needed.
