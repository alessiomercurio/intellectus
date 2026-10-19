---
name: intellectus-analysis
description: >-
  Phase 3 of research. Reads mainly the relevant sections of the sources in
  02-sources.md, checks their context and constraints against 01-scope.md,
  expands needed concepts and writes a cited prose analysis to 03-analysis.md as
  input for the report (not a draft report).
---
# Phase 3 — Analysis

Goal: go from "looks relevant" to "is relevant: here is exactly what it says and under which conditions it holds". Re-read `01-scope.md` first. Analyse **A** sources first, then **B** (for these, the useful part noted in `02-sources.md` is usually enough).

`03-analysis.md` is the working analysis, **not a draft of the report**: write per-source understanding and synthesis; don't write the final answer, recommendations or report structure here.

## Reading (hard rule)
- **Mainly the relevant sections**: abstract, the method/results section that answers a sub-question, the specific table or figure, the Limitations paragraph. For docs: the relevant page. Use search-in-page / section fetches.
- **Full text only in extremis**: when the relevant sections are insufficient (e.g. conditions or definitions are scattered). When you do, write **why** in `03-analysis.md` (`Full text read: <reason>`).
- A concept you don't know: one quick lookup, not a new research. A clearly missing source: add it to `02-sources.md` with a new ID (max 1–2).

## For each source (short prose paragraphs)
1. **Focal point** — which sub-question it answers and how.
2. **Context and constraints** — data, scale, hardware, domain, language, date/version, stated limitations, conflicts of interest; compare with the hard constraints in `01-scope.md`. Outcome: **compatible** · **with adaptations** (which) · **incompatible** (why; may drop to B or be discarded).
3. **Detail** — method/information explained enough to understand or apply it: steps, parameters, exact numbers with units and conditions.
4. **Expanded concepts** — brief explanation of terms/methods needed to understand the answer.

Citations as precise as possible: `[S3, §4.2]`, `[S3, Table 2]`. Mark points **[Fact]**, **[Interp]** (author's view) or **[Inference]** (yours). Paraphrase; quote only short phrases where wording matters.

## Cross-source synthesis
- **Agreement** (raises confidence) · **Contradictions** (and why: data, version, scale) · **Gaps**.

## Output: `03-analysis.md`

```markdown
# Analysis — <title>
## S1 — <short title> (Q1) — compatible
**Focal point:** ...
**Context and constraints:** ...
**Detail:** [Fact] ... [S1, §3]. [Interp] ... [S1, §6]. [Inference] ...
**Expanded concepts:** ...
(Full text read: <reason> — only if it happened)
## S2 — ...
## Cross-source synthesis
Agreement: ... · Contradictions: ... · Gaps: ...
```
