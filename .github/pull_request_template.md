<!--
Title format:  CU-1234 Short description of the change

Keep this small. A pull request that takes more than ~30 minutes to review
will not be reviewed properly. If it has grown to touch unrelated things,
split it.
-->

**Task:** <ClickUp link>

## What changed

<!-- What a reviewer will see in the diff. One or two sentences. -->

## Why

<!-- The reason, not a restatement of the diff. What breaks or stays broken
     without this? If the reason is non-obvious, consider an ADR in
     docs/decisions/ instead of burying it here. -->

## How it was tested

<!-- What you actually did. "Tested locally" is not an answer.
     e.g. added unit tests for X; ran the import against the 500-row sample;
     checked the error path with an invalid token. -->

## Checklist

- [ ] CI is green (lint, tests, build) — **before** requesting review
- [ ] Any new environment variable is added to `.env.example` in this PR
- [ ] …and set in Dokploy for staging and production
- [ ] No secrets, keys, tokens or production data in the diff
- [ ] Database migration is reversible, or the risk is stated below
- [ ] README updated if setup, run or deploy steps changed
- [ ] Troubleshooting entry added if this fixed something non-obvious

## Notes for the reviewer

<!-- Anything worth flagging: a risky area, a deliberate shortcut, a decision
     you are unsure about, a follow-up task already created. Deliberate
     shortcuts belong here — an unrecorded shortcut becomes a defect. -->
