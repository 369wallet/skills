---
name: 369wallet-guide
description: Orientation for the 369wallet Agent ecosystem — primitives, chains, and which skill to reach for in common scenarios.
chains: [arc, giwa, bnb]
---

# 369wallet-guide

Read-first skill. Use this when an agent (or a human reader) lands on the 369wallet skill catalog for the first time and needs to know what each primitive does and which skill solves their task.

## When to use

- First contact with this repository.
- Picking the right skill for a task.
- Understanding how the three supported chains differ.

## Topic map

- Signing & sessions → [`agent-wallet`](../agent-wallet), [`multichain-signing`](../multichain-signing)
- Identity → [`did-identity`](../did-identity)
- Asset management → [`swap-skill`](../swap-skill), [`stake-skill`](../stake-skill), [`transfer-skill`](../transfer-skill), [`balance-portfolio`](../balance-portfolio)
- Payments → [`x402-payment`](../x402-payment)
- MCP surface → [`mcp-wallet-server`](../mcp-wallet-server), [`mcp-chain-server`](../mcp-chain-server)
- Extensibility → [`defi-adapters`](../defi-adapters)

## Chain reference

| Chain | Provider | Distinctive role |
| --- | --- | --- |
| **Arc** | Circle | Native USDC, HTTP 402 settlement chain |
| **Giwa** | Upbit | L2 throughput |
| **BNB** | BNB Chain | Mainstream EVM coverage |

## Common scenarios

- *"Let my agent spend up to $50 USDC on API calls today."* → [`agent-wallet`](../agent-wallet) session + [`x402-payment`](../x402-payment).
- *"Register this agent so it can act across chains under one identity."* → [`did-identity`](../did-identity).
- *"Show me what this address holds across all supported chains."* → [`balance-portfolio`](../balance-portfolio).
- *"Swap USDC to BNB on BNB Chain."* → [`swap-skill`](../swap-skill).
