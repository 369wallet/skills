# Contributing

Thanks for your interest in 369wallet skills.

## Adding a new skill

1. Create a directory at the repo root matching the skill slug (kebab-case).
2. Add `SKILL.md`, `README.md`, `examples/`, and `resources/` following the structure described in [AGENTS.md](./AGENTS.md).
3. Declare supported chains in the SKILL.md frontmatter (`chains: [arc, giwa, bnb]` or a subset).
4. Open a pull request with:
   - The agent use case the skill enables.
   - A runnable example under `examples/`.
   - Any new resources (ABIs, constants) under `resources/`.

## Modifying an existing skill

- Update SKILL.md and README.md together. They must stay consistent.
- If you change the public surface, add an entry to [CHANGELOG.md](./CHANGELOG.md) under `Unreleased`.

## Style

- SKILL.md is for agents — keep it concise.
- README.md is for humans — short prose is fine.
- Examples should run with minimal setup; document any required env vars.

## License

By contributing you agree your work is licensed under [MIT](./LICENSE).
