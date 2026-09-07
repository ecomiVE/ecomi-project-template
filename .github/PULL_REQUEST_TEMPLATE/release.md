<!--
Release: developing -> production

Use this template by adding ?template=release.md to the PR URL.
Title format:  Release vX.Y.Z
-->

## Included

<!-- One line per ClickUp task in this release. Every one must be verified
     on staging before this PR is opened. -->

- CU-____ —
- CU-____ —

## Pre-release checks

- [ ] Every task above is Done and verified on staging
- [ ] CI is green on `developing`
- [ ] Migrations reviewed, and reversible (or the risk is stated below)
- [ ] New environment variables already set in **production** Dokploy
- [ ] No production data or secrets introduced by this diff

## Rollback plan

<!-- How to get back to the previous state, specifically. "Redeploy the
     previous version in Dokploy" is fine — unless there is a migration,
     in which case say what happens to it. -->

## Deploy

- **Release owner:** <one named person, who stays available afterwards>
- **Planned time:** <not Friday afternoon, not before everyone leaves>

## Post-deploy verification

- [ ] Primary user flow walked through by hand in production
- [ ] Error tracking checked for new errors
- [ ] ClickUp tasks moved to Released
- [ ] Client informed, in plain language
