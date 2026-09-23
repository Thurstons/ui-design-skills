# Accessibility Review Checklist

Mark each item with evidence level and status.

## Visual

- Text and meaningful graphics meet the specified contrast targets.
- Focus indicators remain visible against all relevant surfaces.
- State and validation do not rely on color alone.
- Text resizing and zoom do not clip essential content.

## Keyboard

- All interactive controls are reachable and operable.
- Focus order follows the visual and semantic flow.
- Menus, tabs, dialogs, selects, and composite widgets use expected keyboard patterns.
- Focus does not become trapped except intentionally within a modal context.
- Focus returns to a logical element after a dialog closes.

## Semantics

- Controls have accessible names matching visible intent.
- Heading and landmark structure communicates page hierarchy.
- Form labels, instructions, errors, and required state are programmatically connected.
- Icons and images have appropriate alternative treatment.

## Dynamic Behavior

- Loading, success, error, and asynchronous updates are announced appropriately.
- Reduced-motion preferences are honored.
- Timeouts and disappearing messages provide suitable control when required.
- Disabled controls communicate state without blocking necessary recovery.

Visual evidence alone cannot verify keyboard, semantics, screen-reader announcements, or reduced-motion implementation. Mark them `unverified` until tested or supported by code evidence.
