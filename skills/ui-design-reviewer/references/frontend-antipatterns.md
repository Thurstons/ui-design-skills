# Frontend UI Anti-patterns

Check these patterns only when code or runtime evidence is available.

- Page-local “magic numbers” duplicate or override an available design token.
- Repeated component markup diverges instead of using a shared component or variant.
- Specificity escalation or `!important` masks a component contract problem.
- Hover-only controls hide essential actions from keyboard and touch users.
- Click handlers on non-interactive elements lack semantics and keyboard support.
- Fixed dimensions clip translated, zoomed, dynamic, or user-generated content.
- Breakpoints are patched per page with conflicting thresholds.
- Loading state changes layout drastically or permits duplicate submission.
- Disabled styling is applied without disabled behavior, or behavior without visible state.
- Z-index values grow without an overlay-layer system.
- Validation appears only after submission when earlier feedback is required, or fires aggressively before meaningful input.
- Animation uses layout-heavy properties or ignores reduced-motion preferences.

Recommend the smallest shared fix that resolves the root cause. Do not propose a broad refactor when a local correction is sufficient.
