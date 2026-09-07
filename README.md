# <Project name>

> Replace this file's placeholders during project setup. If a section does not
> apply, write "Not applicable" and why — do not delete the heading, so a reader
> can tell the difference between "no database" and "nobody wrote this down".

One or two sentences: what this is and who it is for. A new developer should be
able to read this paragraph and know whether they are in the right repository.

- **Client:** <client name, or "Internal">
- **ClickUp:** <link to the project List>
- **Drive:** <link to the project folder>
- **Staging:** <url>
- **Production:** <url>
- **Status:** <in development / delivered / maintenance / archived>

---

## 1. What it is

What problem this solves, and the shape of the solution. Enough that someone
who has never seen the project can follow a conversation about it.

Keep it to a few paragraphs. If it needs more, that belongs in `docs/`.

### Main components

| Component | Technology | Where it lives |
| --- | --- | --- |
| <e.g. API> | <e.g. FastAPI> | `src/api/` |
| <e.g. Worker> | <e.g. Celery> | `src/worker/` |
| <e.g. Frontend> | <e.g. React> | `web/` |

### External services

| Service | Used for | Account owner |
| --- | --- | --- |
| <e.g. Gemini API> | <e.g. product data extraction> | <Ecomi / client> |

---

## 2. How to run it

> The test for this section: a developer who has never seen this project clones
> it, follows these steps, and gets a running application **without asking
> anyone anything**. If they have to ask, this section is wrong — fix it then,
> not later.

### Prerequisites

- <runtime and version, e.g. Python 3.12>
- <package manager, e.g. uv / pnpm>
- <database, e.g. PostgreSQL 16>
- <anything else that must exist first>

### Setup

```bash
git clone <repo-url>
cd <repo-name>

cp .env.example .env
# Fill in the values. They live in the password manager under "<vault entry>".
# Never commit .env.

<install command>
<database setup / migration command>
<seed command, if there is one>
```

### Run

```bash
<run command>
```

The application is then available at <http://localhost:PORT>.

### Tests and checks

```bash
<test command>
<lint command>
<format command>
```

These are the same commands CI runs. If they pass locally, CI should pass too.

### Known first-run problems

- <the thing that always fails the first time, and the fix>

---

## 3. Environment variables

Every variable is listed in [`.env.example`](.env.example) with a comment
explaining what it is for. That file is the single source of truth for
**names**; the password manager is the single source of truth for **values**.

Rules:

1. A new variable is added to `.env.example` **in the same pull request** that
   introduces it.
2. It is set in Dokploy (staging and production) **before** that pull request is
   merged. This is the most common cause of a broken staging deploy.
3. Variable names are identical across local, staging and production. Only
   values differ.
4. Values are never sent over chat or email, and never committed. If one is
   committed, rotate it — deleting the commit is not sufficient.

---

## 4. How to deploy

Deployment follows the Ecomi delivery workflow. Summary:

| Environment | Branch | Trigger |
| --- | --- | --- |
| Staging | `developing` | Automatic on merge |
| Production | `production` | Manual, in Dokploy |

**Branches**

- `production` — what is live. Protected. Tagged on every release.
- `developing` — integration branch. Protected. Auto-deploys to staging.
- `feature/CU-1234-short-description` — one task, cut from and merged back into
  `developing`.
- `hotfix/CU-1288-short-description` — cut from `production`, merged into both
  `production` and `developing`.

**Releasing**

1. Confirm every included task is verified on staging.
2. Open a pull request from `developing` to `production`, listing the tasks.
3. Check: CI green, migrations reviewed, new environment variables already set
   in production, rollback plan stated.
4. Merge, tag with a semantic version.
5. Deploy manually in Dokploy. One named person runs it and stays available.
6. Verify the primary user flow in production by hand.

**Rollback:** <how to roll back this specific project — previous deployment in
Dokploy, and what to do about migrations>

---

## Documentation

- [`docs/decisions/`](docs/decisions/) — why the significant technical choices
  were made.
- [`docs/troubleshooting.md`](docs/troubleshooting.md) — problems already solved
  once. Add to it while the fix is fresh.

## Conventions

- Tasks live in ClickUp, not in GitHub Issues. The ClickUp ID goes in the branch
  name, the pull request title, and commit messages.
- One task, one branch, one pull request.
- No secrets in the repository, ever.
