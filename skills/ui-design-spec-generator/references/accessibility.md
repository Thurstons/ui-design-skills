# Accessibility Requirements

Use these as baseline design requirements. Match stricter product or legal requirements when supplied.

- Text and interactive states require sufficient contrast; provide targets and verify actual token pairs during implementation.
- Every interactive element must expose a visible `focus-visible` state.
- Mouse-only hover cannot be the sole way to reveal essential information or actions.
- Touch targets should be large enough for reliable activation; use the product standard or propose at least 44 by 44 CSS pixels when no standard exists.
- Inputs need persistent labels or an equivalently clear accessible name; placeholders are not labels.
- Error messages must identify the affected field and explain recovery without relying only on color.
- Dialogs require initial focus, focus containment, Escape behavior when safe, and focus restoration.
- Motion must respect reduced-motion preferences; essential state changes cannot depend solely on animation.
- Content order and keyboard order must remain logical across responsive layouts.
- Icons need text labels or accessible names when their meaning is not decorative or already conveyed by adjacent text.
- Loading, success, and failure changes should be announced appropriately without causing excessive interruption.

Do not claim WCAG conformance from a specification alone. Phrase criteria as requirements to validate in implementation.
