---
name: intellectus-search
description: >-
  Phase 2 of research. Runs targeted online searches, screens results from
  snippets and abstracts only against 01-scope.md, classifies them A / B /
  discarded, and writes a compact 02-sources.md.
---
# Phase 2 — Search and screening

Goal: pick the few sources worth analysing, **from snippets and abstracts only**. Never open full texts in this phase.

## Where
- **Academic**: Google Scholar, Semantic Scholar, arXiv, DBLP, OpenAlex (PubMed for biomedical). Follow citations of one strong paper instead of many keyword queries. Prefer the published version; flag preprints.
- **General**: official docs, repositories, maintainers' blogs, standards, news. Avoid SEO/aggregator pages with no author or date.

## How
- One short query per sub-question, then 1–2 variants if needed. Rephrase rather than repeat.
- Stop as soon as each sub-question has the A-sources required by depth (quick: 3–5 total) or results start repeating. Don't keep searching "just in case".
- Uncovered sub-question after 2–3 attempts → record the gap.

## Screening
For each promising result: read snippet/abstract, compare with `01-scope.md`, classify **A / B / discarded**, and record details immediately (title, authors/org, year, type, reliability, link). Discarded items: just a count, plus one line only for notable ones.

## Output: `02-sources.md`

```markdown
# Sources — <title>
**Queries:** "..." (Scholar), "..." (web)
## A — Relevant
| ID | Title | Authors/Org | Year | Type | Reliability | Link | Q | Why |
## B — Inspiration
| ID | Title | Year | Link | Useful part |
## Discarded: N (notable: ... — reason)
## Coverage: Q1: S1, S3 · Q2: gap (queries tried: ...)
```

IDs (`S1`, `S2`…) stay the same in every later phase.
