# UI Design Skills

[English](README.md) | [简体中文](README.zh-CN.md)

A three-stage UI design workflow for Codex and other AI coding agents. It turns ambiguous, plain-language feedback into implementation-ready specifications and then reviews the finished UI against those specifications.

```text
Plain-language feedback
  ↓ ui-intent-translator
Structured UI Design Brief
  ↓ ui-design-spec-generator
Implementation-ready UI Design Specification
  ↓ Frontend implementation
Page / code
  ↓ ui-design-reviewer
Spec vs Actual + Fix Plan
```

## Skills

| Skill | Question it answers | Primary output |
|---|---|---|
| `ui-intent-translator` | What does the user really mean? | UI Design Brief |
| `ui-design-spec-generator` | How exactly should the interface be designed? | UI Design Specification |
| `ui-design-reviewer` | Does the implementation conform to the specification? | Review Report, comparison matrix, and fix plan |

The responsibilities remain separate: the Translator does not invent CSS values, the Generator does not reinterpret the user's original intent, and the Reviewer does not silently redesign the interface during acceptance review.

## Installation

Copy the desired skill folders into your personal Codex skills directory:

```bash
cp -R skills/ui-intent-translator ~/.codex/skills/
cp -R skills/ui-design-spec-generator ~/.codex/skills/
cp -R skills/ui-design-reviewer ~/.codex/skills/
```

Restart Codex, then invoke a skill explicitly:

```text
$ui-intent-translator This page feels cramped, has too many prominent buttons,
and does not feel polished. Use OpenAI as a style reference.
```

Pass the result to the next stage:

```text
$ui-design-spec-generator Turn the following UI Design Brief into an
implementation-ready specification: ...
```

Review the implementation when it is ready:

```text
$ui-design-reviewer Review the current page screenshots and code against this
UI Design Specification: ...
```

The skills allow implicit discovery by default, so an agent may select them automatically when the request clearly matches their scope.

## Repository Structure

Each skill includes:

- `SKILL.md`: core workflow, responsibility boundaries, and output requirements.
- `agents/openai.yaml`: Codex UI metadata and a default invocation prompt.
- `references/`: terminology, design-system guidance, and review rules loaded only when relevant.
- `schemas/`: machine-validatable JSON Schema contracts.
- `templates/`: reusable Markdown/YAML output templates.

## Design Principles

- Preserve the user's original expressions and explicit constraints so intent is not lost during normalization.
- Keep observation, interpretation, design decisions, and implementation review separate.
- Ground design values in project context, existing design tokens, or explicitly documented assumptions.
- Require the Reviewer to distinguish implementation nonconformance from a specification that may need revision.
- Mark missing evidence as `unverified` instead of presenting inference as fact.

## Before Publishing

Choose and add an open-source license before making the repository public. Evolve terminology and rules from real usage, and avoid turning one product's brand tokens into universal requirements.
