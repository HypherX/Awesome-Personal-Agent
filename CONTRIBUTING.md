# Contributing

Thanks for helping keep **Awesome Personal Agent** up to date.

## What belongs here

**Include** work that is about **personal agents**: agents centered on a *specific user*, combining **personalization** and **proactivity**, with memory as substrate and harness (environment / tools / safety) as capability carrier.

Typical signals:

- Methods or systems that depend on a particular user's preferences, history, devices, or accounts
- Proactivity in a personal-assistant setting (clarification, ask-now-use-later, event-driven initiative, timing / interruptibility)
- Memory mechanisms that support personalization or proactivity across sessions
- Harness work aimed at personal agents (personal MCP/apps, device GUI for one user, isolation / authorization / HITL / injection defenses), including **environment synthesis / training environments built for personal agents**
- Benchmarks and personal-agent harness / safety architecture work aligned with the above

**Exclude** (may go in a future Related section):

- Generic agents with no user specificity (pure SWE, generic web nav, tool-use-only)
- Platform-centric recommendation or fixed-persona roleplay without a real user state loop
- Long-context / document RAG with no personal-user coupling
- Safety / red-team papers that are not about personal-agent harness or personalized assistants

Safety is filed under **Harness**, not as a separate definition axis.

## How to add an entry

1. Verify the arXiv id via [export.arxiv.org/api](https://info.arxiv.org/help/api/index.html) (never invent titles or ids). Non-arXiv items need a stable public URL you have opened.
2. Add one bullet under the **single** primary section that best matches the contribution; put cross-cutting facets in `#tags`.
3. Match the entry format used in `README.md`:

```md
- **Title** [[paper](https://arxiv.org/abs/XXXX.XXXXX)] [[code](https://github.com/...)] — *Venue YYYY.MM* — One-line note. `#tag1` `#tag2`
```

4. Open a PR with the README diff (and LICENSE/CONTRIBUTING only if intentionally changing them).

## Sections

| Section | What goes here |
|---------|----------------|
| Surveys | Surveys / position papers that map personalization, proactivity, or personal agents |
| Personalization | Preference extraction / utilization / update / interaction preference (methods) |
| Proactivity | Clarification, ask-now-use-later, event initiative, timing, proactive memory maintenance (methods) |
| Memory | Architectures, write/retrieve/update, memory→action, when-to-use alignment (methods) |
| Harness | Personal env/tools/MCP/GUI, isolation, authz/HITL, injection/data trust, PA-targeted env synthesis; **safety ∈ harness** |
| Benchmarks | Evaluation suites (end-to-end, atomic, mechanism, harness/safety) |

Prefer newest-first within each section. One primary section per paper.
