---
name: ui-design-spec-generator
description: Turn a structured UI design brief into an implementation-ready and testable UI design specification with design tokens, component states, responsive behavior, and acceptance criteria. Use after design intent has been normalized. Do not use to infer vague user feedback or to review whether an existing implementation conforms to a spec.
---

# UI Design Spec Generator

Convert design intent into decisions a frontend implementer can execute and a reviewer can verify.

## Inputs

Prefer a structured `ui_design_brief`. Also use supplied brand guidelines, design tokens, component-library conventions, screenshots, and repository context. If no structured brief exists, request or first produce one with `ui-intent-translator` when the user language remains ambiguous.

## Workflow

1. Preserve the brief's intent, priorities, `must_keep`, and `must_avoid` constraints. Do not reinterpret colloquial feedback.
2. Inspect existing tokens and component conventions when they are provided or accessible. Reuse them unless the brief explicitly requests a redesign.
3. Resolve the brief into measurable rules. Read [design-system rules](references/design-system-rules.md) for token decisions, [component specs](references/component-specs.md) for states and anatomy, [responsive rules](references/responsive-rules.md) for breakpoint behavior, and [accessibility](references/accessibility.md) for required interaction and contrast constraints.
4. State each assumption that affects a numeric value. If multiple valid systems remain, select one coherent default and explain the choice; do not mix arbitrary values from unrelated systems.
5. Return the ten required sections using [the template](templates/ui-design-spec.md). Keep machine-readable output compatible with [the JSON Schema](schemas/ui-design-spec.schema.json).

## Specification Rules

- Express dimensions with units and identify whether they are fixed, minimum, maximum, or fluid.
- Use semantic tokens before raw values: `color.text.primary`, `space.lg`, `radius.card`.
- Define component anatomy, variants, sizes, states, content behavior, and accessibility behavior when relevant.
- Define behavior at each relevant breakpoint, not just breakpoint numbers.
- Include empty, loading, error, disabled, focus, selected, and overflow states where the component can encounter them.
- Make acceptance criteria observable. Replace “more premium” with checks such as “one dominant primary action per task region” or “all spacing values use the declared scale.”
- Preserve framework and component-library constraints. A specification should not require a new dependency unless the user requested it or the existing stack cannot express the requirement.
- Use WCAG-oriented requirements as a floor, while avoiding unsupported compliance claims.

## Boundary

Answer only: **How exactly should it be designed?**

Do not re-interpret the user's original vague language, generate production code, or claim that an implementation passes. Implementation belongs to a coding task; conformance belongs to `ui-design-reviewer`.

## Required Output

The specification must contain:

1. design direction and governing principles;
2. layout system;
3. spacing system;
4. typography system;
5. semantic color system;
6. component specifications;
7. interaction and motion specifications;
8. responsive rules;
9. Do / Don't constraints;
10. acceptance criteria.

Also include provenance for reused tokens and an `assumptions` section for decisions not grounded in provided evidence.
