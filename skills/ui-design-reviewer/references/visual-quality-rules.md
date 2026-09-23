# Visual Quality Review

## Layout

Check container bounds, grid structure, alignment, region proportions, navigation dimensions, content order, clipping, overlap, and scroll ownership. Evaluate both intended viewport widths and widths between breakpoints.

## Spacing

Check page padding, section rhythm, component gaps, internal padding, token usage, and whether spacing communicates grouping. Repeated off-scale values usually indicate token drift.

## Typography

Check semantic hierarchy, size, line-height, weight, width, wrapping, truncation, numeric alignment, and readability. Verify the role, not only the raw value.

## Color and Depth

Check semantic token use, text hierarchy, contrast, focus indication, state distinction, borders, shadows, overlays, blur, and dark/light theme behavior when specified.

## Components

Check anatomy, size, variants, content limits, interaction states, empty/loading/error states, and consistency between instances. A component may visually match while behaving incorrectly.

## Hierarchy

Check the first focal point, primary task, CTA hierarchy, progressive disclosure, competing accents, and whether secondary information stays secondary.

## Motion

Check purpose, duration, easing, continuity, interruption, loading feedback, and reduced-motion behavior. Motion should clarify state or spatial relationship.

## Responsive

Check reflow, content priority, target size, navigation transformation, action overflow, table strategy, dialog sizing, typography, and unwanted horizontal scroll.

Do not convert subjective preference into a failure unless it contradicts an explicit spec or produces an observable usability problem.
