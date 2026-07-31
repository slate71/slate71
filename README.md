# I deploy AI to radically improve margins in service businesses

**The problem.** A California WDO (wood-destroying-organism) inspection company's
most expensive, licensed labor was bottlenecked by mandatory paperwork — every
inspection legally requires a specific state-board report, and inspectors were
spending hours after each job hand-writing it instead of billing field time.
That's the margin compression I set out to remove.

**The constraint.** The report isn't freeform text a model can improvise — it's
a regulated legal document where errors carry licensing consequences. So the
success bar was never "does the AI write something plausible." It's "does this
pass side-by-side review against a licensed inspector's own compliant report."
The real legal artifact is the benchmark.

**The architecture.** I deliberately didn't build this as an agent. In a
regulated workflow you want determinism and inspectability, so the LLM stays
confined to narrow, typed steps — voice in, structured findings out — never
roaming free over a legal document: capture → transcription → findings
extraction → report generation → filing → audit trail. Tenant isolation is
schema-per-tenant with row-level security in Postgres, not just separate
containers, because RLS is the boundary that survives an audit. Trust comes
from a human in the loop plus an eval harness — a spec, a scoreboard, a
stopping condition, scored against golden cases from the field — so "good
enough" is measured, not a vibe. The one place I *did* go agentic is the build
itself: an eval-gated SDLC where a coding agent takes a ready issue, writes a
failing eval, and codes until it's green behind a taste-critic and a human
merge. Built by agents, doesn't run as one. Underneath it all is an event
stream that's more than logging — it's the provenance backbone, and the
foundation for the field app to behave like a sensor instead of a form. The
layer I'm adding next extends that same core to agents: an MCP server over the
API, so a REST API serves the field app and MCP serves agents — two consumers,
one regulated core.

**Where it stands.** Field capture and findings extraction are live in
production. Report generation is the stage now being built and validated
against that same side-by-side bar, with field validation next. The
before-state is already measured, not estimated — pulled from the operator's
own system-of-record history: a median of 3 days from inspection to report
entry, 0% same-day, three office staff batch-retyping every report by hand.
That's the number the system has to beat, and it's falsifiable by the same
queries once it does.

Because it's built as reusable primitives — not bespoke code — this is tenant
one of a platform pattern for deploying AI into regulated service workflows,
not a dead end.

## Background

10+ years building interfaces and leading engineering teams. Former Chapter
Lead at Airbyte; led platform modernization and an 8-person team at
HouseCanary.

## Work with me

Open to consulting engagements in applied AI and regulated-domain automation.

- [WDO Desk](https://wdodesk.com)
- [LinkedIn](https://linkedin.com/in/llandersen)
- [Email](mailto:luke@slate71.com)
