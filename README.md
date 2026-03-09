# DF StoryForge

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

DF StoryForge is an open-source web app for [Dwarf Fortress](https://www.bay12games.com/dwarves/) players to upload game exports and automatically generate **stories** and **comics** from their worlds.

## Features

- **User accounts** – Sign up, log in, and manage your content (auth via AWS Cognito).
- **Free quota + paid credits** – Start with free story/comic generations; buy more credits via Stripe when you need them.
- **Upload exports** – Upload DF or DFHack export files; the app queues generation jobs.
- **Background generation** – A worker turns your exports into narrative stories and comic-style outputs.
- **View & download** – Browse your library and download stories/comics.
- **DFHack scripts** – Download scripts (coming later) to pull richer game data from Dwarf Fortress for better stories.

## Tech stack

- **Frontend + API**: [Next.js](https://nextjs.org/) (TypeScript), App Router
- **Auth**: [AWS Cognito](https://aws.amazon.com/cognito/) + [NextAuth](https://nextauthjs.org/) in the app
- **Payments**: [Stripe](https://stripe.com/) (Checkout + webhooks for credit packs)
- **Database**: PostgreSQL on [AWS RDS](https://aws.amazon.com/rds/)
- **Storage**: [Amazon S3](https://aws.amazon.com/s3/)
- **Background jobs**: [Amazon SQS](https://aws.amazon.com/sqs/) + worker container
- **Hosting**: AWS ([App Runner](https://aws.amazon.com/apprunner/) or ECS Fargate) with Docker

## Repository structure

- **`apps/web`** – Next.js app (UI, API routes, Stripe webhooks).
- **`apps/worker`** – Node/TS worker that consumes SQS and runs story/comic generation.
- **`packages/shared`** – Shared TypeScript types and utilities.
- **`infra/`** – Infrastructure-as-code (AWS resources).
- **`docs/`** – Setup, deployment, and DFHack script docs.
- **`prompts/`** – Curated prompts and responses used to design and build this project (so others can follow the same process).

## Status

This repo is in **early development**: architecture and skeleton are in place. The goal is a working, deployable app and a reproducible, open build process.

- **[ARCHITECTURE.md](ARCHITECTURE.md)** – Full system design, data model, and AWS components.
- **[docs/](docs/)** – Setup and deployment guides.
- **[prompts/](prompts/)** – Step-by-step prompts used to build the app.

## How this project was built

The design and implementation were driven by AI-assisted conversations. The `prompts/` directory contains the main prompts and summarized (or full) responses so you can:

- Understand why certain choices were made.
- Replay or adapt the process for your own project.
- Learn the architecture and deployment steps.

See [prompts/README.md](prompts/README.md) for the index and how to follow along.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for local setup, code style, and how to submit pull requests.

## License

MIT – see [LICENSE](LICENSE).
