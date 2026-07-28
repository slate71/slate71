# Building regulated compliance software for pest control operators

I build **WDO Desk** — software that turns a termite inspector's spoken
walkthrough into a structured, review-ready state inspection report. Live in
production with a California WDO operator since July 2026.

## What it does

- Captures a field inspection by voice and diagram, offline-capable, on a tablet
- Extracts findings in the regulation's own terms (CA WDO Form 43M-41) — the
  model is structurally constrained to the regulation's taxonomy, it can't
  invent a finding code
- A person reviews every finding before anything is filed — nothing files itself
- Every correction becomes a permanent test case the system has to pass from
  then on

## How it's built

- Multi-tenant platform (internal name: Anvil), schema-per-tenant isolation,
  Postgres + Drizzle, deployed on Railway and Cloudflare
- An eval-gated, self-improving dev loop: failing test case → code → full gate
  (lint, types, tests, evals) → PR behind automated + human review
- The moat is provenance and auditability, not speed — every finding traces
  back to its source capture and model version

## Background

10+ years building interfaces and leading engineering teams. Former Chapter
Lead at Airbyte; led platform modernization and an 8-person team at
HouseCanary.

## Work with me

Open to consulting engagements in applied AI and regulated-domain automation.

- [WDO Desk](https://wdodesk.com)
- [LinkedIn](https://linkedin.com/in/llandersen)
- [Email](mailto:luke@slate71.com)
