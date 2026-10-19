---
name: intellectus-orchestrator
description: >-
  Entry point for any research request, academic or general. Sets mode and depth
  (quick by default), runs the scoping, search, analysis and report phases in
  order with at most 5 subagents and a token budget, hands the report to the
  research reviewer bot for up to two review cycles, and manages the hand-off
  files.
---
# Research orchestrator

Use at the start of every research request. It does no research itself: it picks mode and depth, then calls the other skills in order.

## Budget rules (hard)
- **Max 5 subagents per research run, total.** Use as few as the work needs (often 1–2); add more only for clearly independent parts. Never spawn one per source.
- **Fresh subagent per run.** Always start a new one; never resume a subagent that carries context from a previous research.
- Pass subagents file paths, not pasted content.

## Token budget (hard)
Most cost is context re-read on every step, not generated output. So:
- **Lean starts.** Each subagent gets a short prompt: goal, the relevant sub-question(s), paths to `01-scope.md` and any input file, and what to write where. Never paste sources, PDFs or previous reports into a prompt.
- **Restart between phases.** Each phase's result lives in its file (`01`–`04`); start the next phase from those files, not from the accumulated conversation. Don't let one agent grow past ~150k tokens of context: save state to the phase file and continue fresh.
- **Store notes, not pages.** Keep extracted passages and numbers in `02-sources.md`; don't re-open a source already summarised there.
- **Review rounds reuse files.** For a second review cycle send only the updated report and the list of changes, not the whole set again.

## Language
- Talk to the user, and write `04-report.md`, in the **user's language**. Keep source titles, quotes and technical terms in the original. For academic work always include English queries.

## 1. Set up
1. Working folder `research/<slug>/`.
2. **Mode**: academic (methods, results, papers) · general (tools, docs, practices, news) · mixed.
3. **Depth** — **quick is the default.** Use standard/deep only if the user asks.

| Depth | Sub-questions | A-sources | Review |
|---|---|---|---|
| Quick (default) | 1–2 | 3–5 | up to 2 cycles |
| Standard | 2–4 | 5–8 | up to 2 cycles |
| Deep (on request) | 3–6 | 8–15 | up to 2 cycles |

## 2. Phases
1. `intellectus-scoping` → `01-scope.md`
2. `intellectus-search` → `02-sources.md`
3. Coverage check: every sub-question has an A-source, or the gap is written down. One extra search round at most.
4. `intellectus-analysis` → `03-analysis.md` (prose analysis, not a draft report)
5. `intellectus-report` → `04-report.md` (the only deliverable)
6. Send only `01-scope.md`, `02-sources.md`, `04-report.md` to the reviewer.

## 3. Review outcome (`05-review.md`) — max 2 cycles
- **APPROVED** → deliver.
- **APPROVED WITH FIXES** → apply the listed fixes (targeted: only the points named), then deliver.
- **REJECTED** → redo what is listed (returning to search/analysis if needed), update the report, and send it back to the reviewer for a **second review** (`05-review-2.md`), with only the updated report and a list of changes.
- After the second review: apply its fixes and deliver. No third cycle.
- Fixes you can't apply → "Unverified points" section at the top of the report.

## Rules for every phase
- `01-scope.md` is the anchor for every relevance judgement.
- The citation is born with the information (`[S3]`).
- Never invent sources, authors, DOIs or numbers.
- Distinguish what the source states, what its author interprets, what you infer.
- Read selectively: mainly relevant sections/tables; full text only in extremis, with the reason noted in `03-analysis.md`.
