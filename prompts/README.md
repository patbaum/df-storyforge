# Build prompts – how this project was built

This folder contains the main **prompts** (and summarized or full **responses**) from the AI-assisted conversations used to design and build DF StoryForge. The goal is to make the process **reproducible**: someone else can follow the same steps and reasoning to understand or recreate the app.

## How to use these prompts

- **Read in order** – Files are numbered (e.g. `000-`, `010-`) to suggest a sequence.
- **Copy and adapt** – You can paste a prompt into your own AI assistant (e.g. Cursor, ChatGPT) and adapt the context (e.g. your repo name, your AWS account) to get a similar design or implementation.
- **Extend** – When you add a major feature or doc, consider adding a new file (e.g. `040-deployment-setup.md`) with the prompt and a short summary of the response.

## Index

| File | Topic |
|------|--------|
| [000-architecture-planning.md](000-architecture-planning.md) | Initial product idea, architecture doc, tech stack (Next.js, Cognito, Stripe, AWS), data model, and deployment approach |

More files will be added as auth, payments, UI, worker, and deployment are implemented.

## Design history

The full architecture is documented in the repo root: [ARCHITECTURE.md](../ARCHITECTURE.md). That doc was produced from the architecture-planning conversation and refined as needed.
