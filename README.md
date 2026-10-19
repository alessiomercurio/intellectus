<p align="center">
  <img src="assets/intellectus-banner.png" alt="Intellectus" width="100%">
</p>

Intellectus is a set of research skills that makes AI agents something you can trust when they do research, academic or general. It follows a workflow close to how people actually research: every phase writes its own file, every claim is cited, and a separate agent reviews the result.

## Workflow

| Phase | Skill | Output |
|---|---|---|
| 1. Scoping | `intellectus-scoping` | `01-scope.md`: main question, sub-questions, hard constraints |
| 2. Search | `intellectus-search` | `02-sources.md`: screens snippets and abstracts only, ranks sources A or B |
| 3. Analysis | `intellectus-analysis` | `03-analysis.md`: reads only the relevant sections, checks every source against the constraints |
| 4. Report | `intellectus-report` | `04-report.md`: the only deliverable, every claim cited |
| 5. Review | `intellectus-review` | `05-review.md`: a separate agent checks sources and key citations, runs a counter-search, and sends the report back if something is off (max 2 cycles) |

`intellectus-orchestrator` is the entry point: it sets mode (academic, general or mixed) and depth, runs the phases in order and handles the review cycles.

Depth is **quick** by default (3–5 core sources); **standard** (5–8) and **deep** (8–15) are available on request. A run uses at most 5 subagents, and agents pass each other file paths instead of whole documents, to keep token usage low.

## Installation

**Cursor (and other coding agents)**: install all the skills with the [skills CLI](https://github.com/vercel-labs/skills):

```bash
npx skills add alessiomercurio/intellectus -a cursor
```

Add `-g` to install them for every project instead of the current one.

**Grok Bot**: give the skills to your Grok Bots directly, by sharing this repo (or the skill folders) with a bot and asking it to save them as its skills.
