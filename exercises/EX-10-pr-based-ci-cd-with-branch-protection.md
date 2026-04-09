# EX-10: PR-Based CI/CD with Branch Protection

## Use This After

- [LAB-05: Full CI/CD Flow](../labs/LAB-05-full-cicd-flow.md)
- preferably [EX-09: Full Flow Failure and Recovery](EX-09-full-flow-failure-and-recovery.md)

## Goal

Finish the course with a real team workflow:

- CI runs on pull requests to `main`
- branch protection requires CI to pass
- CD runs only after the pull request is merged

## Build

Create these workflow files yourself:

- `.github/workflows/05-pr-ci-exercise.yml`
- `.github/workflows/05-cd-after-pr-merge-exercise.yml`

Reference solutions: instructor repo only.

## Requirements

### Workflow 1: PR CI

- Create `.github/workflows/05-pr-ci-exercise.yml`.
- The workflow should start on pull requests to `main`.
- The workflow should run when the pull request is opened, updated, or reopened.
- The workflow should run the project tests.
- The workflow should use one stable job name such as `verify`.

### Workflow 2: CD After Merge

- Create `.github/workflows/05-cd-after-pr-merge-exercise.yml`.
- The workflow should start when a pull request to `main` is closed.
- The workflow should continue only if the pull request was really merged.
- The workflow can stay small and use one clear CD message or simple step.

### Branch Protection

- Configure `main` so changes come through pull requests.
- Configure `main` so the CI check must pass before merge.
- If your GitHub plan allows it, also block direct pushes to `main`.

## Suggested Flow

1. create a feature branch
2. make one safe change
3. open a pull request to `main`
4. watch PR CI run
5. confirm merge is blocked until CI passes
6. merge the pull request
7. watch CD run after merge

## Acceptance Criteria

- Opening a pull request to `main` starts the PR CI workflow.
- The PR shows the CI result clearly before merge.
- Merge stays blocked until the required CI check passes.
- Merging the pull request starts the CD workflow.
- Closing a pull request without merging does not run the CD job or CD steps.
- You can explain why branch protection turns CI into a real team rule.
