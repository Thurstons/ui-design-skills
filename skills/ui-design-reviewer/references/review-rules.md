# Review Rules

## Evidence Levels

- `measured`: obtained from DOM, computed style, test, or deterministic code path.
- `observed`: clearly visible in an original screenshot or live UI.
- `inferred`: likely from indirect evidence; needs confirmation.
- `unverified`: evidence is unavailable or insufficient.

Every failure must include at least `measured` or `observed` evidence. Use inferred evidence to direct investigation, not to assert a defect.

## Status Logic

- `pass`: actual behavior matches the specified rule within its stated tolerance.
- `fail`: actual behavior conflicts with a required rule.
- `partial`: some states, instances, or viewports conform and others do not.
- `unverified`: the test could not be completed.
- `not_applicable`: the rule does not apply, with a reason.

## Overall Result

- `fail`: any critical issue, or the release policy says a major issue blocks release.
- `partial_pass`: no critical issue, but minor failures or unverified required checks remain and the release policy permits a partial result.
- `pass`: all required checks verified and no blocking issue remains.

If no release policy exists, state the default used.

## Issue Quality

Each issue should include:

- a stable ID;
- conformance type;
- severity and category;
- exact specification reference;
- actual result and evidence level;
- location and affected scope;
- user or system impact;
- recommended correction;
- expected verifiable result.

Group repeated instances caused by one shared token or component. Split issues when fixes, owners, or risks differ.

## Spec Revision

A suspected spec problem does not make the current implementation conform. Record it separately with:

- current spec;
- concern and evidence;
- affected flows;
- proposed revision;
- approval needed.
