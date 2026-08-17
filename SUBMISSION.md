# Composio Toolkit Research — Submission Package

**Candidate:** Harsh Kapoor  
**Assignment:** Toolkit Research Operations — 100 App Case Study  
**Repository:** https://github.com/iamharshkapoor/-composio-toolkit-research

## Package contents

| Location | What the reviewer receives |
|---|---|
| `case-study/index.html` | The final self-explanatory interactive HTML case study. It includes the 100-app matrix, app/API/auth/MCP search, global filters, evidence drawers, buildability queues, verification disclosure, methodology, and direct source-repository link. |
| `case-study/assets/` | Compiled JavaScript and CSS required to render the page. |
| `case-study/data/` | Reviewer-facing canonical dataset, quality report, verification log, holdout disclosure, calculated insights, and Composio dry-run proof. |
| `source/` | Editable source code, deterministic research-processing scripts, datasets, and the full README. |
| `source/README.md` | Exact local runbook for the research pipeline and static case-study site. |

## How to review

The static case study is in `case-study/`. From that directory, serve the page locally with any static server, for example:

```bash
npx serve .
```

Then open the locally printed URL. The research table, search, filters, evidence links, and JSON/CSV artifacts are fully client-side.

## How to run the research agent pipeline

Follow `source/README.md`. The core reproducible sequence is:

```bash
cd source
pnpm install
node scripts/process_research.mjs
node scripts/generate_verification_sample.mjs
node scripts/reconcile_verification.mjs
node scripts/generate_insights.mjs
node scripts/composio_proof.mjs
node scripts/validate_research.mjs
pnpm dev
```

## Integrity note

The first-pass audit, correction sample, and post-repair holdout are explicitly disclosed in the case study. The Composio proof artifact is labelled as a dry run unless an approved read-only test connection is configured. No secrets or production-account actions are included.
