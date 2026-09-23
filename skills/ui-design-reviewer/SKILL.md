---
name: ui-design-reviewer
description: Review a UI implementation against an explicit design specification using screenshots, browser evidence, DOM, or frontend code. Produce evidence-based conformance findings, a Spec vs Actual matrix, severity-ranked issues, and an actionable fix plan. Do not use to create a new visual direction or silently rewrite the governing specification.
---

# UI Design Reviewer

Verify implementation against the governing design specification. Report what is observable, what is inferred, and what remains unverified.

## Inputs and Evidence

Use the UI Design Spec plus any available screenshots, live URL, DOM, computed styles, component code, design tokens, and viewport details. Capture or inspect the implementation before making visual findings when tools permit.

If no design specification is supplied, do not claim conformance. Offer a clearly labeled `baseline_audit` based on common usability and accessibility expectations, or ask for the spec when strict acceptance is required.

## Workflow

1. Establish the governing spec version, implementation version, inspected viewports, and evidence sources.
2. Convert the spec's acceptance criteria and component rules into a checklist.
3. Inspect the implementation across the relevant states and viewports. Use [review rules](references/review-rules.md) for evidence and severity, [visual quality rules](references/visual-quality-rules.md) for layout and hierarchy, [accessibility checklist](references/accessibility-checklist.md) for interaction checks, and [frontend anti-patterns](references/frontend-antipatterns.md) for implementation-specific risks.
4. Build a Spec vs Actual matrix. Mark each item `pass`, `fail`, `partial`, or `unverified`.
5. Write one issue for each actionable root cause, not one issue for every repeated symptom. Give tight locations and evidence.
6. Prioritize a fix plan. Include exact code changes only when code evidence supports the file, selector, component, and expected value.
7. Return the report using [the template](templates/ui-review-report.md), compatible with [the JSON Schema](schemas/ui-review-report.schema.json) when machine-readable output is requested.

## Review Dimensions

Cover each applicable dimension:

1. layout;
2. spacing;
3. typography;
4. color and contrast;
5. components and states;
6. visual hierarchy;
7. interaction and motion;
8. responsive behavior;
9. accessibility;
10. design and frontend anti-patterns.

Mark an inapplicable dimension as `not_applicable` with a reason rather than fabricating findings.

## Governing Rules

- Do not reject a conforming implementation because another design “looks better.”
- Do not silently replace the spec. Findings must state either `implementation_nonconformance` or `spec_revision_suggestion`.
- A spec revision suggestion must quote or identify the current rule, explain the conflict or usability concern, and propose a reviewable revision. Continue judging the current implementation against the current approved spec.
- Do not infer exact pixel values from a resized screenshot. Label estimates and use DOM/computed styles when exactness matters.
- Do not report code-level locations when only screenshot evidence exists.
- Do not claim accessibility compliance from visual inspection alone. Mark keyboard, screen reader, focus management, or reduced-motion behavior unverified unless tested or established in code.
- Deduplicate shared-component issues and list affected instances.
- Prefer fixes that restore tokens or shared components over page-local overrides.

## Severity

- `critical`: blocks a core task, hides content, causes severe overflow, creates inaccessible core interaction, or violates a release-blocking criterion.
- `major`: clearly violates the spec and materially harms hierarchy, usability, responsiveness, or consistency.
- `minor`: localized inconsistency with limited task impact.
- `suggestion`: optional improvement outside required conformance.

## Required Output

Include:

- review summary and overall status;
- evidence scope and limitations;
- dimension coverage;
- Spec vs Actual matrix;
- severity-ranked issues with specification, actual, evidence, location, impact, recommendation, and expected result;
- prioritized fix plan;
- code-change candidates only when verified;
- spec revision suggestions, kept separate from conformance issues;
- retest checklist and unverified items.

Use `pass` only when all release-blocking criteria were verified and no critical or major failures remain. Use `partial_pass` when required evidence is incomplete or only minor failures remain according to the supplied release policy.
