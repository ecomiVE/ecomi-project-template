# Template setup

> **Delete this file once setup is complete.** Its presence in a project
> repository means setup was never finished.

This repository is the Ecomi project template. Everything below happens at
**T-5 days**, before the project start date — see the delivery workflow
document.

## Publishing the template (once, for the organisation)

1. Create the repository in the Ecomi organisation as `ecomi-project-template`.
2. Push these files.
3. **Settings → General → check "Template repository".**
4. Set the default branch to `developing`.
5. Create branch protection rules for `production` and `developing`:
   - Require a pull request before merging
   - Require approvals: 1
   - Require status checks to pass: `Lint, test, build`, `Secret scan`
   - Do not allow bypassing the above

## Starting a new project from it

1. **Use this template → Create a new repository.** Private.
2. Create the `production` branch from `developing`, and apply the branch
   protection rules above to both.
3. Work through the checklist below.
4. Delete this file and commit.

## Setup checklist

**README**

- [ ] Project name, client, and the ClickUp / Drive / staging / production links
- [ ] Section 1: what it is, components table, external services table
- [ ] Section 2: prerequisites, setup, run, test commands — **verified on a
      clean machine**, not from memory
- [ ] Section 4: rollback plan specific to this project

**Environment**

- [ ] `.env.example` trimmed to the blocks this project actually uses
- [ ] Every variable has a comment saying what it is for
- [ ] Vault entry created in the password manager, shared with the team
- [ ] Variables set in Dokploy for **both** staging and production

**CI**

- [ ] Stack block uncommented in `.github/workflows/ci.yml`, others deleted
- [ ] Placeholder step removed
- [ ] CI green on an empty commit — before the start date

**Docs**

- [ ] `docs/decisions/0001` dated and deciders named
- [ ] Example entry deleted from `docs/troubleshooting.md`

**Dokploy**

- [ ] Staging application created, deploying automatically from `developing`
- [ ] Production application created, manual deploy from `production`
- [ ] Empty skeleton deployed to staging — prove the pipeline works before
      there is anything to break it

**Last check**

- [ ] Another developer clones the repo and gets it running from the README
      alone, without asking you anything. If they have to ask, fix the README
      now rather than at handover.
- [ ] This file deleted.

## What is deliberately not here

- **Issue templates.** Tasks live in ClickUp. Two task systems means neither is
  trusted.
- **A licence.** Client work is private. Add one only for something published.
- **Application code, linters, formatters.** Stack-specific — add them with the
  first commit, and make sure the commands match README section 2 and CI.
