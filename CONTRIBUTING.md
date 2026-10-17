# Contributing to MyPill

## Workflow

1. Branch from `main`. Name the branch after the change: `feat/dose-reminders`,
   `fix/reconnect`, `chore/bump-deps`.
2. Open a pull request early, as a draft if it isn't ready.
3. CI must be green and one other person must approve before merging.
4. Squash-merge, so `main` keeps one commit per pull request.

## Commit and PR titles

Short and in the imperative: "Add dose reminder", not "Added..." or "Adds...".

## Before you open a pull request

- Never commit real patient data, secrets or personal data, even in tests or logs.
- Call out anything that changes when a dose is given or how it is recorded,
  and include a test that shows the old and new behaviour.

## Shared CI

Add the organization's secret scan to a repository's `.github/workflows/ci.yml`:

```yaml
jobs:
  secret-scan:
    uses: MyPill-project/.github/.github/workflows/secret-scan.yml@main
```
