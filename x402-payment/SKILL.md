---
name: x402-payment
description: Handle HTTP 402 payment-required flows end-to-end, settled in USDC on Arc.
chains: [arc]
---

# x402-payment

Intercept HTTP 402 responses, negotiate the payment requirement, sign the USDC transfer on Arc, retry the original request with the payment proof header, and return the resolved response.

## When to use

- Agent is paying for API access, content, or services that gate on HTTP 402.
- Wallet-native payment without a middleware proxy.

## Capabilities

- `request(url, options)` — fetch wrapper that auto-handles 402.
- `payInvoice(invoice)` — sign and settle a specific 402 invoice manually.
- `verifyProof(proof)` — confirm settlement on-chain.

## Inputs

- Standard fetch `url` and `options`.
- Invoice payload: `{ payTo, amount, asset, chain, nonce, expiresAt }`.

## Outputs

- HTTP response with payment receipt header attached, plus on-chain settlement tx hash.

## Notes

- Settlement asset is **USDC on Arc**. Other chains are not supported for x402 today.
- Spending caps can be enforced via [`agent-wallet`](../agent-wallet) sessions.
