# Troubleshooting

Problems already solved once, so the next occurrence takes minutes.

**Add an entry when** something cost you more than about fifteen minutes and the
cause was not obvious from the error message. Write it while the fix is fresh —
an entry written at the end of the project is written from memory, and memory is
where the useful details go missing.

Newest entries at the top.

---

## Template — copy this

### <Symptom, as you would search for it>

- **Symptoms:** what you see. Include the literal error text — that is what the
  next person will paste into a search box.
- **When it happens:** first run, after a deploy, only on staging, under load.
- **Cause:** what is actually wrong, if known.
- **How to investigate:** the commands or logs that confirm it.
- **Fix:** the steps. If it is a workaround rather than a fix, say so.
- **Last confirmed:** YYYY-MM-DD

---

<!-- Example of a filled entry. Delete it once this file has real content. -->

### Staging deploy succeeds but the app returns 500 on startup

- **Symptoms:** Dokploy reports a successful deploy; every request returns 500.
  Logs show a KeyError or "missing required environment variable".
- **When it happens:** after merging a pull request that introduced a new
  environment variable.
- **Cause:** the variable was added to `.env.example` but never set in Dokploy.
  Local works because the developer set it in their own `.env`.
- **How to investigate:** compare the variable names in `.env.example` against
  the environment tab of the Dokploy application.
- **Fix:** add the missing variable in Dokploy and redeploy. To prevent it: set
  new variables in Dokploy *before* merging the pull request that adds them.
- **Last confirmed:** YYYY-MM-DD
