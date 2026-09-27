# scriptorium-docs

**The public half of scriptorium's output.** Product documentation for Beacon (a
fictional status-page product), drafted by an agent from PRDs and designs, reviewed on a
Jira ticket, and published here only after a human approved the content *and* a human
merged the pull request.

Live site: **https://scriptorium-docs.vercel.app/**

## How a page gets here

1. **Scribe** (the drafting agent) works a Jira ticket: it checks the PRD has a feature,
   an audience and a user goal, drafts the page, lints it, and revises it on reviewer
   feedback.
2. A reviewer comments `approve` on the ticket. That approves the *content*.
3. The agent pushes the page to a per-ticket branch (`docs/<ticket>-<slug>`) and opens a
   pull request from its own GitHub App identity.
4. A human merges the pull request. That *publishes* it — the agent never pushes `main`.
5. Vercel builds `sites/external` from `main`, and the page is live.

Two gates on purpose: approving what a page says and deciding it goes public are separate
decisions, and each one is recorded — the approver in the commit message, the merger on
the pull request.

## What to look at

- **`git log`** — every publish names its ticket and its approver:
  `docs: rate-limit-dashboard (DOC-10, approved by …)`. The author is the agent; the
  approver is the record. There is no database behind it.
- **`docs/`** — the published pages, plain markdown with a small frontmatter block
  (`jira_issue`, `published_at`). Internal material — PRDs, open questions, the agent's
  house rules — lives in a separate private repository and never touches this one.

## Layout

| Path | What it is |
|---|---|
| `docs/` | The published pages. Written by the agent, merged by a human. |
| `sites/external/` | Astro + Starlight site. `scripts/sync-content.mjs` copies `docs/` — and only `docs/` — into the build. |

## Run the site locally

```bash
cd sites/external
npm ci
npm run dev
```

## Editing by hand

Allowed. The pages are plain markdown. If you change a page the agent published, the
agent notices on its next publish of that page and refuses to overwrite your edit — it
reports the conflict on the originating ticket instead.
