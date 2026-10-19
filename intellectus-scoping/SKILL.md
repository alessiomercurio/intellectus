---
name: intellectus-scoping
description: >-
  Phase 1 of research. Turns the request into sub-questions, constraints and
  relevance criteria written to a short 01-scope.md, the reference for every
  later phase and for the reviewer.
---
# Phase 1 — Understand the request

Goal: write down **what is being looked for and why**, briefly. Keep `01-scope.md` under ~30 lines.

## Steps
1. **Main question** in one sentence; **expected answer** (comparison, method, state of the art, fact, recommendation).
2. **Sub-questions**: as many as the depth allows (quick: 1–2). Each must be answerable.
3. **Project context** (from the message/project files): system, **hard constraints** (budget, hardware, licence, language, deadlines), what was already tried or ruled out. Hard constraints decide applicability later.
4. **Relevance criteria**: A = same problem, compatible constraints; B = partially similar, useful for ideas; else discarded.
5. **Ambiguity**: if readings diverge a lot and the user is reachable, ask **one** question; otherwise record an assumption.
6. **Mode**, a few keywords (incl. English), time window if relevant.

## Output: `01-scope.md`

```markdown
# Scope — <title>
**Main question:** ...   **Expected answer:** ...
**Mode:** ...   **Depth:** quick | standard | deep
## Sub-questions
- Q1: ...
## Context and hard constraints
- ...
## Out of scope
- ...
## Relevance: A = ... · B = ...
## Keywords / window: ...
## Assumptions: ...
```
