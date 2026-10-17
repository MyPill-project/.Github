# Contributing to MyPill

## Workflow

1. Branch from `main`. Name the branch after the change: `feat/dose-reminders`,
   `fix/ble-reconnect`, `chore/bump-nest`.
2. Open a pull request early, as a draft if it isn't ready.
3. CI must be green and one other person must approve before merging.
4. Squash-merge, so `main` keeps one commit per pull request.

## Commit and PR titles

Short and in the imperative: "Add weight-based intake validator", not
"Added..." or "Adds...".

## Changes that need extra care

- **API contract**: changing the OpenAPI document in `platform` regenerates
  `@platform/api-client` and can break the mobile app and the device API that
  `firmware` relies on. Say so in the PR.
- **Dose scheduling and intake records**: anything that can change when a dose
  is due, or whether an intake is recorded, needs a test that shows the old and
  new behaviour.
- **Firmware releases**: production images are signed offline, never in CI.
- **Infrastructure**: CI never applies. Paste the `tofu plan` output in the PR.
- **Health data**: never commit real patient data, even in fixtures or logs.
