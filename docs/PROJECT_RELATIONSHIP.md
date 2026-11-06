# Anchor Task Assurance and ActionGate

**Anchor is the protocol home with reference code. ActionGate is the enforcement toolkit.** Keep both repositories, product names and package namespaces. Neither repository is being merged, renamed, archived or replaced by this documentation cleanup.

## Responsibilities

| Question | Owning project or component |
| --- | --- |
| What evidence and verification should this answer require? | Anchor's AGP methodology, configured for the company's workflow. |
| Does the supplied record satisfy the reference answer-release rules? | The reference gate in `agp/core.py`, or ActionGate's separately packaged evidence gate. |
| May this agent call this tool with these exact arguments? | ActionGate's action broker plus host-owned authorization policy. |
| Who is the reviewer, and may they approve this business action? | The company's authenticated application and review process. |
| Where are company-wide state, durable audit records and provider credentials protected? | The production integration. These are not supplied by the protocol or completed by the current in-memory toolkit. |

## Current code relationship

Checked baselines on November 6, 2026:

- Anchor `0.2.1`, commit `5b14fb85c0d03d3ef90a0ea5a310b915451aa32a`, distribution `anchor-task-assurance`, import `agp`.
- ActionGate `0.3.1`, commit `3dcaee44cb96cf4b7265c655d459e3f546c3625a`, distribution and import `actiongate`.

At those commits, the two `core.py` files have identical text after normalizing line endings and share `agp-reference-controls-0.2.0`. They are separately packaged copies, not a live dependency. ActionGate additionally owns `runtime.py` and its tool authorization, reviews, autonomy, breaker and usage controls. Its broker requires ActionGate's own `ReleaseDecision` type; Python objects from the separate `agp` package are not automatically interchangeable.

This inspection documents the current relationship. It is not a new conformance test, certification or permanent promise of synchronization. A production adapter between packages must validate trusted values and preserve binding to the exact reviewed result. A serialized `RELEASE` string or a receipt alone must never mint permission to act.

## One company example, two decisions

A customer-service assistant proposes a refund explanation. The workflow supplies the current company policy, case facts and a draft. Trusted checks establish source applicability, actual support and any required review. The evidence gate decides whether the explanation may be delivered.

If a refund is then proposed, ActionGate separately checks the authenticated agent subject, allowed customer/case, exact amount and tool arguments, autonomy setting and required review. A manager's approval is tied to that particular proposed action. The host retains credentials and executes only through the protected path. Even a supported explanation is not a refund authorization.

The repositories already have separate synthetic evidence and action demos. A single joined demonstration with real model integration and independently checked evidence remains a future milestone. Do not advertise it as shipped or claim measured accuracy gains from the existing demos.

## Cleanup now and engineering next

This cleanup clarifies README entry points, links the canonical protocol documentation and labels ActionGate's copied research documents as reference snapshots. It preserves working imports, commands, licenses, historical grants and runtime behavior.

The next bounded engineering milestone is a joined synthetic company demonstration with exact draft/action binding and tests for stale evidence, withheld output, changed action arguments, unauthorized review and ticket replay. Before consolidating the duplicated evidence code, define a shared serialized contract and decision fixtures, verify compatibility and choose a versioned dependency or explicit adapter. Code deduplication can then be reviewed independently; repository merger is unnecessary for that work.

## Suggested GitHub About descriptions

These are proposed metadata text, not a claim that repository settings were updated:

- **Anchor:** `AGP evidence-and-review protocol for AI task results, with Python reference controls and evaluation tools.`
- **ActionGate:** `Python enforcement toolkit for AI agents: scoped tool actions, approvals, autonomy limits and evidence-release checks.`

Repository descriptions and pinned cards should link these two roles clearly. Publicly visible source does not grant additional usage rights; the existing license and historical grants continue to apply.
