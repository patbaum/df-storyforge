# AWS setup guide

This document will cover one-time AWS setup for DF StoryForge: account, IAM, and initial resource creation (Cognito, RDS, S3, SQS, ECR, App Runner or ECS). It is a placeholder until the exact steps are finalized during implementation.

## Planned sections

- AWS account and root/user best practices
- IAM user or role for CI/CD and local deployment
- Creating the Cognito User Pool and app client
- Creating the RDS PostgreSQL instance and database
- Creating the S3 bucket and folder structure
- Creating the SQS queue and dead-letter queue
- ECR repositories for `web` and `worker` images
- App Runner services (or ECS cluster, task definitions, and services)
- SSM Parameter Store or Secrets Manager for DB URL, Stripe webhook secret, etc.
- Route 53 hosted zone and ACM certificate (if using a custom domain)

Check back as the project is built; this doc will be filled in step by step.
