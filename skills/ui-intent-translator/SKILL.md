---
name: ui-intent-translator
description: Convert plain-language UI feedback, aesthetic preferences, and product comments into a structured, professional UI design brief. Use when the user describes how a page feels or should feel but has not yet supplied implementation-ready design requirements. Do not use to write CSS, choose exact design tokens, or review an existing implementation against a specification.
---

# UI Intent Translator

Translate what the user means without prematurely deciding how to implement it. Preserve the user's original language, explicit constraints, product context, and priorities.

## Workflow

1. Identify the page type, primary user task, available evidence, and any existing design-system constraints.
2. Split each statement into observation, interpretation, intent, and constraint.
3. Map interpretations to professional terminology. Read [UI terminology](references/ui-terminology.md) for ambiguous colloquial phrases, [style dictionary](references/style-dictionary.md) for named visual directions, and [anti-patterns](references/anti-patterns.md) when feedback concerns visual clutter or weak hierarchy.
4. Infer only what the evidence supports. Record assumptions and unresolved choices separately. Ask a question only when different answers would materially change the design direction; otherwise proceed with a stated assumption.
5. Return a structured brief using [the template](templates/design-brief.md). Keep it compatible with [the JSON Schema](schemas/design-brief.schema.json) when machine-readable output is requested.

## Interpretation Rules

- Do not perform mechanical word replacement. “右边太空” may indicate visual imbalance, an unsuitable grid ratio, or misplaced secondary content; it does not automatically mean “add more components.”
- Treat references such as “像 Apple” or “像 OpenAI” as shorthand for observable traits. Extract traits such as generous whitespace, editorial hierarchy, neutral color, or restrained motion. Do not instruct the next stage to clone a brand.
- Separate a problem from a proposed solution. If the user says “加张卡片，这里太空,” retain the proposed card but also express the underlying balance problem so the next stage can evaluate better solutions.
- Do not invent user research, business goals, brand colors, target devices, or technical constraints.
- When screenshots or code are supplied, distinguish observed facts from interpretation.
- Use bilingual terminology where it improves handoff, for example `过度容器化 (over-containerization)`.

## Boundary

Answer only: **What does the user mean?**

Do not output exact pixel values, color hex values, CSS, component APIs, or implementation steps. Those belong to `ui-design-spec-generator`. Do not judge conformance of an implementation; that belongs to `ui-design-reviewer`.

## Required Output

Produce `ui_design_brief` with:

- context and page type, each with evidence or confidence;
- concise intent summary;
- normalized problems linked back to original expressions;
- visual direction and reference traits;
- layout, typography, color, component, interaction, and UX intent;
- `must_keep` and `must_avoid` constraints;
- assumptions and unresolved decisions;
- a short handoff note for the specification generator.

Prefer YAML for human review and JSON when the caller requests machine validation. Omit empty optional sections only when they are truly irrelevant; never hide uncertainty by filling them with invented details.
