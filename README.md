# Evidence Ledger — Composio Toolkit Research Case Study

Evidence Ledger is an evidence-backed research operations case study covering the 100 apps specified in the Composio assignment. It evaluates the practical credential path, API surface, MCP status, toolkit buildability, evidence quality, and verification outcome for every record.

## What is included

| Artifact | Purpose |
|---|---|
| `data/research_results_final.json` | Canonical reconciled 100-app dataset with claim-specific evidence links. |
| `data/research_results_final.csv` | Reviewer-friendly export of the final research matrix. |
| `data/verification_log.csv` | Field-by-field independent sample review, including matches and corrections. |
| `data/quality_report.json` | Structural validation output and flags. |
| `data/insights.json` | Deterministically calculated dashboard and pattern-analysis values. |
| `data/composio_proof.json` | Clearly labelled dry-run / proof-of-work status. |
| `scripts/` | Reproducible research processing, validation, verification reconciliation, insights, and proof runner. |
| `client/` | The interactive single-page HTML case study generated from the reconciled data. |

## Submission links

| Item | Link / location |
|---|---|
| Source repository | https://github.com/iamharshkapoor/-composio-toolkit-research |
| Upload-package guide | `SUBMISSION.md` |
| Compiled static case study | `dist/public/index.html` after `pnpm build` |

## Run locally

```bash
pnpm install
node scripts/process_research.mjs
node scripts/generate_verification_sample.mjs
node scripts/reconcile_verification.mjs
node scripts/generate_insights.mjs
node scripts/composio_proof.mjs
node scripts/validate_research.mjs
pnpm dev
```

The local static project is served by Vite. Use `pnpm build` and `pnpm check` before deployment.

## Research workflow

The first pass was gathered in independent parallel app-research tasks against public vendor documentation. The data processor normalises the records, applies evidence and taxonomy checks, and selects a high-information verification sample. The second pass independently verifies 25 apps, intentionally prioritising MCP claims, access gates, low-confidence records, and higher-risk domains. The reconciler preserves first-pass values, applies verified corrections, and produces field-level and record-level accuracy metrics.

The verification sample is **not a random probability sample**. It is an error-discovery audit. Any final alignment rate after applying sample corrections refers only to the same correction sample and must not be read as a generalised accuracy estimate.

## Composio proof boundary

`scripts/composio_proof.mjs` produces a traceable dry-run artifact if `COMPOSIO_API_KEY` and an approved, read-only test connection are not available. It does not claim a live SDK or MCP call. To convert the dry run into a live demonstration, set a Composio API key and configure an approved read-only test toolkit connection, then update the runner with the official current Composio SDK/session and tool-discovery call for that environment.

## Source policy

Official API, authentication, app-review, pricing, help-centre, and vendor-owned repository pages are prioritised. A missing source is represented as `unknown`, not converted into a negative conclusion. Findings are time-bound to **17 August 2026** and may change as vendors evolve their APIs and MCP support.

## Safety

No secrets are stored in this repository. No production CRM, messaging, payment, customer, or account action was carried out. The case study uses public documentation research and a labelled proof-of-work dry run only.
