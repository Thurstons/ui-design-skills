# Component Specification Guide

Specify only components used by the page, but cover each one completely enough to implement.

## Required Fields

- purpose and hierarchy;
- anatomy and content slots;
- variants and sizes;
- default, hover, active, focus-visible, disabled, loading, selected, error, and success states where applicable;
- truncation, wrapping, empty content, and overflow behavior;
- mouse, touch, and keyboard behavior;
- relevant semantic tokens;
- acceptance checks.

## Common Component Concerns

### Button

Define primary-action limit per task region, label rules, icon placement, minimum target size, loading label behavior, disabled semantics, and focus visibility.

### Card / Surface

State when a container is warranted. Define padding, grouping, clickable affordance, selected state, and whether nested cards are allowed. Do not use elevation as decoration.

### Table

Define column priority, alignment, sorting, filtering, sticky behavior, row actions, selection, loading, empty/error states, overflow, and narrow-screen alternative.

### Form, Input, Select

Define label placement, required/optional indication, helper and error text, validation timing, clear behavior, search behavior, multiple selection, keyboard access, and long-value handling.

### Navigation, Tabs, Sidebar

Define active state, hierarchy, overflow, collapse behavior, keyboard behavior, persistence, and mobile transformation.

### Dialog / Drawer

Define trigger, title and description, size bounds, focus trap, close routes, destructive-action confirmation, scroll ownership, and mobile behavior.

### Feedback

Define inline versus global messages, duration, dismiss behavior, retry behavior, and whether the message survives navigation.
