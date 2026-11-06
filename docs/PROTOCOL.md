# Anchor protocol: overview and document map

**Name:** Anchor Task Assurance. **Status:** experimental reference protocol; existing methodology specification 0.2. This is a documented operating procedure for AI task assurance, not an established industry standard or a network/wire protocol.

Anchor is the protocol home and includes a Python reference implementation under the import `anchor_task_assurance`. [ActionGate](https://github.com/R-Mijo/ActionGate) is the companion software toolkit for release checks and tool-action enforcement. The two repositories remain separate.

## The operating procedure

| Phase | Required work in the existing methodology | Responsible party |
| --- | --- | --- |
| Qualify | Frame the task, classify its consequences and evidence needs, assign appropriate controls. | Accountable workflow owner and trusted application. |
| Compile | Select applicable sources, choose generation and verification methods, constrain access and actions. | Application integration and designated source/policy owners. |
| Assure | Produce a draft, verify the actual output against evidence, apply the release decision and preserve a bound record. | Generator, trusted checking process and authorized reviewer where required. |

The protocol requires a clear separation between a generator's assertions and trusted evidence/verification inputs. Sources must be applicable; citations need actual support; required checks must be performed. Material uncertainty, conflicts and unsupported claims affect whether the output is delivered, withheld or escalated. An action requires a separate authorization process.

This overview introduces no new scoring thresholds, protocol version or behavior. The documents below define the existing design and its limits.

## Where each definition lives

| Document or code | Purpose |
| --- | --- |
| [METHODOLOGY.md](METHODOLOGY.md) | Operational method: nine stages, task characteristics, provisional assurance/verification levels, evidence and release rules. |
| [APPLY_TO_YOUR_WORKFLOW.md](APPLY_TO_YOUR_WORKFLOW.md) | Integration responsibilities: generation, trusted verification, exact-draft binding, enforcement and authenticated review. |
| [Reference gate](../anchor_task_assurance/core.py) | Exact behavior of this Python implementation. Current code policy identifier: `anchor-reference-controls-0.2.2`. Package version and policy identifier are separate. |
| [VALIDATION_PROTOCOL.md](VALIDATION_PROTOCOL.md) | Research/evaluation plan. This is the protocol for studying Anchor, not the operating procedure or proof that Anchor improves accuracy. |
| [RELATED_WORK.md](RELATED_WORK.md) and [CRITICAL_REVIEW.md](CRITICAL_REVIEW.md) | Prior work, limitations and claims that have not been established. |
| [PROJECT_RELATIONSHIP.md](PROJECT_RELATIONSHIP.md) | Boundaries, current package relationship and one company example spanning Anchor and ActionGate. |

## What the reference code can establish

The `anchor_task_assurance` package checks typed profiles, claim/source references, source validity dates, required check flags, review settings and release outcomes. It produces checksum-protected receipts. The current implementation accepts trusted verifier findings; it does not independently establish their truth, complete claim coverage, authentic approval identity or semantic evidence support. A checksum is not a signature. The application must enforce a withheld decision and protect the reviewed draft from substitution.

## Reading and adopting the method

Start with the methodology, assign an owner for one workflow and define its evidence and required review. Use the reference implementation to inspect the gate behavior. Add an application adapter and validate it with allowed, stale, missing, conflicting and unauthorized cases. The proposed shared demonstration is a supported refund explanation followed by a separately authorized synthetic refund action; see the relationship document. That joined demonstration and empirical model evaluation remain work to complete.

Documentation visibility does not create new implementation or commercial permissions. Existing repository licenses and historical grants remain as stated in [the license](../LICENSE) and [licensing history](LICENSING_HISTORY.md).
