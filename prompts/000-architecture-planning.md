# 000 – Architecture planning

This prompt led to the initial architecture document, tech stack choices, data model, and deployment strategy for DF StoryForge.

## User prompt

> Based on this app (DFLegendsCompanion) and the other one we worked on (DFComicMaker) I would like to create a new website where other players of Dwarf Fortress can come and upload game data exports and the site will generate basic comics and stories. To facilitate this we'll (later) create and make available for download some new DFHack scripts that pull more interesting game data.
>
> I would like the site to authenticate users so they have an account and need to log in. Each user will have a free story generation quota after which I want them to pay for more credits.
>
> Could you create an architecture doc that specifies everything needed to build and deploy the app. Please research and advise on options for user accounts and payment services. I assume we'll host on AWS with docker. Obviously we'll need a nice looking website.
>
> I've never built or deployed an app like this - so please think of everything I need. I'm going to use the architecture doc as input to actually build and deploy the app.

(Follow-up: user said they have no strong preference on stack and want a **lightweight, inexpensive** solution with **not much usage** expected.)

## Assistant response (summary)

- **Product**: Web app for Dwarf Fortress players to upload exports and generate stories/comics; auth required; free quota then paid credits.
- **Tech stack**:
  - **Frontend + API**: Next.js (TypeScript), App Router.
  - **Auth**: AWS Cognito + NextAuth in the app (low cost, good free tier).
  - **Payments**: Stripe (Checkout + webhooks for credit packs).
  - **Database**: PostgreSQL on AWS RDS.
  - **Storage**: S3 for uploads and generated assets.
  - **Background jobs**: SQS + a separate worker container (Next.js enqueues; worker runs generation).
  - **Hosting**: AWS with Docker – App Runner recommended for simplicity; ECS Fargate as alternative.
- **Features**: Sign-up/login, profile, credits and billing, upload flow, job queue, story/comic viewers, library, and a public DFHack scripts page.
- **Data model**: Tables for users, credit_transactions, uploads, jobs, stories, comics, comic_panels, and optional webhook_events for idempotent Stripe handling.
- **Infrastructure**: Route 53, ACM, ECR, App Runner (or ECS), RDS, S3, SQS, Cognito, SSM/Secrets Manager, CloudWatch.

The full architecture (diagrams, data model, AWS components, security, and UI outline) was written into **ARCHITECTURE.md** in the repo root. See [ARCHITECTURE.md](../ARCHITECTURE.md).

## Notes

- Cognito was chosen for cost and AWS integration; Stripe for mature API and credit-pack billing.
- App Runner was recommended over ECS for lower operational overhead at low traffic.
- Free tier and small instance sizes (e.g. RDS `db.t4g.micro`) keep cost low for light usage.
