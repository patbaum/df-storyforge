# Contributing to DF StoryForge

Thanks for your interest in contributing. This project is open source (MIT) and we welcome pull requests and issues.

## Local development (planned)

Once the codebase is in place, you will be able to:

1. **Clone and install**
   - Clone the repo and install dependencies (e.g. `pnpm install` at repo root for the monorepo).
   - Copy `.env.example` to `.env` and fill in local values (DB URL, Cognito app client, Stripe test keys, S3/SQS endpoints for localstack or MinIO/ElasticMQ).

2. **Run locally**
   - Start local services with `docker-compose` (Postgres, optional S3/SQS emulators).
   - Run the Next.js app: `pnpm --filter web dev`.
   - Run the worker: `pnpm --filter worker dev` (or equivalent).

3. **Code style**
   - TypeScript strict mode. Follow existing formatting (Prettier/ESLint config in repo).
   - Prefer small, focused commits and PRs.

4. **Submitting changes**
   - Open an issue or comment on an existing one if the change is large.
   - Branch from `main`, make your changes, run tests and lint, then open a PR against `main`.
   - Ensure CI (lint + tests) passes.

## Prompts and design history

The `prompts/` directory holds the prompts and responses used to design and build this app. If you extend the system (e.g. new features, new infra), consider adding a new prompt file (e.g. `040-feature-name.md`) so others can follow the same reasoning. See [prompts/README.md](prompts/README.md).

## Questions

Open a [GitHub Discussion](https://github.com/patbaum/df-storyforge/discussions) or an [Issue](https://github.com/patbaum/df-storyforge/issues) for questions or ideas.
