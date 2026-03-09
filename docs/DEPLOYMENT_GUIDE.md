# Deployment guide

This document will describe how to build the Docker images, push them to ECR, and deploy (or update) the web app and worker on AWS App Runner or ECS. It is a placeholder until the pipeline is implemented.

## Planned sections

- Prerequisites (AWS CLI, Docker, env vars or SSM access)
- Building the `web` and `worker` images
- Pushing images to ECR
- Deploying/updating the App Runner services (or ECS services)
- Rolling back
- CI/CD with GitHub Actions (trigger on push to `main`, build, push, deploy)

Check back as the project is built; this doc will be filled in step by step.
