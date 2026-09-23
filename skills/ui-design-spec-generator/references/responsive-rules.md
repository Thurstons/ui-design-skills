# Responsive Rules

Breakpoints should follow the existing product when available. If none exist, use content-driven ranges and declare them as proposed.

For every range specify:

- container width and horizontal padding;
- column count and gutter;
- navigation transformation;
- content reflow and priority;
- toolbar and action overflow;
- table behavior;
- modal or drawer behavior;
- type and spacing adjustments;
- minimum touch target and horizontal-overflow expectations.

## Fallback Ranges

```yaml
wide: ">= 1440px"
desktop: "1200px-1439px"
compact_desktop: "1024px-1199px"
tablet: "768px-1023px"
mobile: "< 768px"
```

These are starting points. Move a breakpoint when the content fails, not merely because a popular device width exists.

## Transformation Examples

- Multi-column dashboard: reduce optional side regions before collapsing the primary task flow.
- Sidebar: compact or overlay drawer according to navigation frequency and available space.
- Toolbar: keep the core action visible; move secondary actions to an overflow menu.
- Table: prioritize columns, permit controlled horizontal scroll, or use a list/card representation when row comparison is not essential.
- Dialog: use bounded width on desktop and near-full viewport or drawer treatment on small screens.

Acceptance criteria should test at boundary widths and between named widths, not only at exact preset devices.
