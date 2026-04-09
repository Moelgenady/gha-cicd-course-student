# EX-08: Build and Run With GitHub Variables

## Use This After

- [LAB-04: Deploy Workflow](../labs/LAB-04-deploy-workflow.md)

## Goal

Practice one smaller build-and-run flow on the same runner.

The new GitHub Actions idea here is reading normal configuration from repository variables.

## Before You Start

Create repository variables here:

`Settings -> Secrets and variables -> Actions -> Variables`

Create:

- `PYTHON_BASE_IMAGE` = `python:3.12-slim`
- `APP_PORT` = `8000`

Use normal repository variables for this exercise.

Do not use secrets.

Do not use GitHub environments.

Placeholder screenshot target:

`docs/images/repository-variables-page.png`

## Build

Create this workflow file yourself:

- `.github/workflows/04-build-and-run-with-vars-exercise.yml`

Use this supporting file from the repo:

- `Dockerfile.arg-base`

Reference solution: instructor repo only.

## Requirements

- Create one workflow in `.github/workflows/04-build-and-run-with-vars-exercise.yml`.
- The workflow should build the image, start the container, and check the app on the same runner.
- The workflow should read `${{ vars.PYTHON_BASE_IMAGE }}` and `${{ vars.APP_PORT }}` from repository variables.
- The workflow should fail clearly if a required variable is missing.
- The workflow should pass the base image into Docker with `--build-arg`.
- The workflow should run the health check after startup.

## Acceptance Criteria

- The logs show that the repository variables were read during the workflow.
- The logs show that those values affected both the build step and the run step.
- The app starts and the health check runs successfully.
- You can explain how this differs from Lab 04.
- You can explain why these values are variables, not secrets.
