# .github

Organization-wide defaults for the MyPill repositories (`platform`, `firmware`,
`infra`). This repository is **public**, because GitHub only reads default
files from a public `.github` repository. Never put secrets, internal hostnames
or patient data here.

## What's here

| Path | Purpose |
| --- | --- |
| `pull_request_template.md` | Default PR description for every repo |
| `.github/ISSUE_TEMPLATE/` | Default bug and feature forms |
| `CONTRIBUTING.md` | How we branch, review and merge |
| `SECURITY.md` | How to report a vulnerability |
| `.github/workflows/secret-scan.yml` | Reusable workflow: scans git history for leaked secrets |
| `.github/workflows/ci.yml` | CI for this repo: lints the workflows and scans itself |

A repository that has its own file of a given type (for example its own
`.github/pull_request_template.md`) uses that instead of the default here.
`CODEOWNERS` and Dependabot config can't be shared this way; each repo keeps its own.

## Using the reusable workflows

Add a job to a repository's `.github/workflows/ci.yml`:

```yaml
jobs:
  secret-scan:
    uses: MyPill-project/.github/.github/workflows/secret-scan.yml@main
```

The doubled `.github` is correct: the repository is named `.github`, and workflows live in its
`.github/workflows` folder.
