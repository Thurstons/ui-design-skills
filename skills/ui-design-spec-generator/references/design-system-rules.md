# Design System Rules

## Token Priority

Choose values in this order:

1. Existing product design tokens.
2. Existing component-library variables and patterns.
3. Brand guidelines supplied by the user.
4. A coherent default system declared as an assumption.

Do not overwrite established tokens merely because another system looks more fashionable.

## Spacing

Use a small, coherent scale. A reasonable fallback is:

```yaml
space:
  1: 4px
  2: 8px
  3: 12px
  4: 16px
  6: 24px
  8: 32px
  10: 40px
  12: 48px
  16: 64px
  20: 80px
```

Treat this as a fallback, not a universal mandate. Map each usage to a token rather than scattering raw values.

## Typography

Specify at least page title, section title, component title, body, secondary text, label, caption, KPI/numeric value, and code when relevant. For each role define size, line-height, weight, and color token. Avoid creating roles that differ by only one insignificant value.

## Color

Define semantic roles rather than component-specific colors:

- page, surface, elevated, overlay;
- text primary, secondary, tertiary, inverse, disabled;
- border subtle, default, strong, focus;
- brand primary and interaction states;
- success, warning, danger, info and their text/surface/border variants.

State contrast targets for text and interactive states. Do not claim a contrast ratio without calculation or a cited token source.

## Radius, Border, and Elevation

Use few levels. Each level must express hierarchy or state. Avoid combining a strong border, strong shadow, gradient, and blur on the same ordinary surface.

## Provenance

For each token group, mark one of:

- `existing`: copied from the supplied system;
- `adapted`: derived from an existing token with a stated reason;
- `proposed`: introduced because no source token exists.
