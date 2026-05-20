# x402-payment

HTTP 402 payments settled in USDC on Arc.

Drop in a fetch-shaped wrapper; the skill intercepts 402 responses, signs the USDC transfer on Arc, retries the request with a payment-proof header, and returns the resolved response.

## Chains

Arc (USDC settlement only)

## Status

🚧 Scaffolded — implementation in progress.

See [SKILL.md](./SKILL.md).
