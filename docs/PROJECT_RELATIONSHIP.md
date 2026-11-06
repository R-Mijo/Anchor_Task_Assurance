# Anchor Task Assurance and ActionGate

**Anchor is the protocol home with reference code. ActionGate is the enforcement toolkit.** Keep both repositories and product names. The Anchor Python namespace is `anchor_task_assurance`; ActionGate uses `actiongate`. This cleanup does not combine the repositories.

## Responsibilities

| Question | Owning project or component |
| --- | --- |
| What evidence and verification should this answer require? | Anchor's methodology, configured for the company's workflow. |
| Does the supplied record satisfy the reference answer-release rules? | The reference gate in `anchor_task_assurance/core.py`, or ActionGate's separately packaged evidence gate. |
| May this agent call this tool with these exact arguments? | ActionGate's action broker plus host-owned authorization policy. |
| Who is the reviewer, and may they approve this business action? | The company's authenticated application and review process. |
| Where are company-wide state, durable audit records and provider credentials protected? | The production integration. These are not supplied by the protocol or completed by the current in-memory toolkit. |

## Current code relationship

This proposed revision prepares Anchor `0.2.2` (distribution `anchor-task-assurance`, import `anchor_task_assurance`, command `anchor`) and ActionGate `0.3.2` (distribution/import/command `actiongate`). It builds on the reviewed source history at Anchor `5b14fb85c0d03d3ef90a0ea5a310b915451aa32a` and ActionGate `3dcaee44cb96cf4b7265c655d459e3f546c3625a`; those ancestor commits do not represent the newly prepared versions.

The current `core.py` files are identical after normalizing line endings and share `anchor-reference-controls-0.2.2`. They are separately packaged copies, not a live dependency. ActionGate additionally owns `runtime.py` and its tool authorization, reviews, autonomy, breaker and usage controls. Its broker requires ActionGate's own `ReleaseDecision` type; Python objects from `anchor_task_assurance` are not automatically interchangeable.

This inspection documents the current relationship. It is not a new conformance test, certification or permanent promise of synchronization. A production adapter between packages must validate trusted values and preserve binding to the exact reviewed result. A serialized `RELEASE` string or a receipt alone must never mint permission to act.

## One company example, two decisions

A customer-service assistant proposes a refund explanation. The workflow supplies the current company policy, case facts and a draft. Trusted checks establish source applicability, actual support and any required review. The evidence gate decides whether the explanation may be delivered.

If a refund is then proposed, ActionGate separately checks the authenticated agent subject, allowed customer/case, exact amount and tool arguments, autonomy setting and required review. A manager's approval is tied to that particular proposed action. The host retains credentials and executes only through the protected path. Even a supported explanation is not a refund authorization.

The repositories already have separate synthetic evidence and action demos. A single joined demonstration with real model integration and independently checked evidence remains a future milestone. Do not advertise it as shipped or claim measured accuracy gains from the existing demos.

## Cleanup now and engineering next

This cleanup clarifies README entry points, links the canonical protocol documentation and labels ActionGate's copied research documents as reference snapshots. It updates the Anchor import, shared policy/study labels and one manifest key. Existing licensing, historical grants and enforcement/scoring rules are preserved. Use the current import and prepare fresh studies after updating.

The next bounded engineering milestone is a joined synthetic company demonstration with exact draft/action binding and tests for stale evidence, withheld output, changed action arguments, unauthorized review and ticket replay. Before consolidating the duplicated evidence code, define a shared serialized contract and decision fixtures, verify compatibility and choose a versioned dependency or explicit adapter. Code deduplication can then be reviewed independently; repository merger is unnecessary for that work.

## Suggested GitHub About descriptions

These are proposed metadata text, not a claim that repository settings were updated:

- **Anchor:** `Anchor evidence-and-review protocol for AI task results, with Python reference controls and evaluation tools.`
- **ActionGate:** `Python enforcement toolkit for AI agents: scoped tool actions, approvals, autonomy limits and evidence-release checks.`

Repository descriptions and pinned cards should link these two roles clearly. Publicly visible source does not grant additional usage rights; the existing license and historical grants continue to apply.
