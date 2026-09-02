# External-pressure campaign — decision date 2026-10-03

> **FROZEN HISTORICAL RECORD.** `protocol-ecosystem` was retired as an active
> coordination surface on 2026-09-02. The schedules, active streams, budgets,
> and future decision language below preserve the last campaign state; they are
> not current instructions or portfolio status. See [`RETIREMENT.md`](RETIREMENT.md).

**This is a coordination plan, not a source of protocol semantics.** Nothing here
grants, upgrades, or withdraws any protocol status. Member repositories do not
depend on it, and no row in [`README.md`](README.md) may cite it as a gate. If
this document and a member repository disagree about that repository, the member
repository is right.

## Why it exists

Every question answered so far has been internal: is the ecosystem consistent
with itself. The three questions that decide whether it should keep growing are
not, and none of them can be answered by another review round:

1. Can an outside person use Warrant without help from its authors?
2. Does Σ-GLYPH have a measurable advantage over a restricted WASM profile on a
   non-trivial task?
3. Does Decision Archaeology matter to anyone with a real case of their own?

**No external signal by the decision date is itself an answer**, and it leads to
freezing rather than to another internal cycle.

## Baseline (2026-08-22)

| Repository | Branch | Revision | Last CI on that branch |
| --- | --- | --- | --- |
| sigma-glyph | master | `01069d0410e6fc3b37d5dfeea1c58939e7ff6350` | x1-cross-repo: success |
| warrant | master | `ecece1c22043d307b891a205817d880280c7a797` | x1-cross-repo: success |
| oaip | main | `2ac421c471e7e7a666610db70671003fbdede97c` | dependabot workflow: success |
| BOS | main | `e9b8ab775aef18542ff37842f6fa67e7020161f4` | BOS gate: success |
| sev | master | `33a08a60d811ef634f3ea69b868d6983197ab936` | model: success |
| decision-archaeology | main | `2828e1d012916e60cf9511628044cf6461f578f6` | Toolchain: success |
| protocol-ecosystem | master | `57d557ed4db974aed29b65ba46efa385706f33fa` | map-check: success |

Green CI is the baseline of this campaign, not evidence for any of its three
questions. Every result recorded below cites an exact revision.

## Active and frozen

| Stream | State | Budget | Owner-side limit |
| --- | --- | --- | --- |
| Warrant — one usable vertical, dogfooded | active | 50% | no new protocol, repository or governance layer |
| Σ-GLYPH / WASM bake-off — a kill test, not development | active | 40% | preregistration merged; fixtures frozen before implementation |
| Decision Archaeology | **frozen** | 0% | returns only for a real, unmodelled case |
| Ecosystem map and technical hygiene | active | 5% | documentation defects only |
| OAIP | maintenance-only | — | security, CI, compatibility, false documentation |
| BOS | **frozen pending external demand** | 0% | security, broken CI, critical dependencies, false documentation |
| SEV | **abandoned and GitHub-archived 2026-09-02** | 0% | preservation, security, and correction of false historical claims only; reactivation requires a new owner act |

BOS keeps its existing `research` status in the map. SEV no longer does: after
the terminal refund-slice negative result, closure of the Warrant receipt
direction, and absence of a consumer, the owner ended the trajectory as
`ABANDONED`. The map uses its closed relation status `historical`; this does not
mean refuted or losslessly superseded.

## Rules

- No new repositories, protocols, governance layers, or general abstractions.
- A protocol need may be opened only after a runnable demonstration that the
  existing contracts cannot express the operation.
- A model reviewing this work is not an external check. Neither is the author,
  nor the ecosystem owner.
- No claim of adoption, review, or endorsement without a direct act by the party
  named.
- No repeat model review without a new change or a new counterexample.
- Every public artifact states one claim, one command that checks it, and one
  condition that would refute it.
- Prefer a re-executable check to persuasive prose where the question can be
  reduced honestly. Do not encode semantic or legal judgment merely to make it
  executable; record the residual trust boundary and competing interpretations
  instead.

## Success criteria

**Warrant.** One workflow its own authors want to leave switched on in their own
repositories: an agent-made change produces a single artifact showing what
changed, what proposed it, which policy was in force, which evidence was checked,
which reason can be re-executed, and what would break the verdict. Judged by
setup time, time to a verdict a reviewer understands, manual steps required,
tampering actually caught, and whether it reduces review work. If it does not, the
vertical is removed rather than polished.

An independent install remains the only thing that would count as external
signal, but **it is no longer something this campaign goes looking for** — see
the outreach decision below.

**Σ-GLYPH.** Numeric thresholds are fixed in the preregistration before any
implementation exists, and the result is published whichever side wins. If
Σ-GLYPH cannot do the task inside the declared budget it is not a general default
runtime; if it loses on practical metrics without demonstrating a property an
outside user needs, its status becomes an optional specialised runtime. If the
WASM profile fails to reproduce determinism or its resource bounds, it is not
called a drop-in replacement.

**Decision Archaeology.** One external case with a named consumer, lawful and
sufficient inputs, at least one independently re-run check, and a recorded
verdict: useful, not useful, or blocked. Absent that by the decision date, DA
goes to maintenance.

## Outreach: cancelled, not deferred

**Owner decision, 2026-08-23: cold outreach is cancelled as a line of work.** No
recipients are to be assembled and nobody is to be contacted. The draft shortlist
and message prepared under the previous plan are withdrawn and were never sent.

The reasoning is not politeness. A cold message measures the sender's existing
reach, not the artifact: a reply says something about who is asking, and silence
says nothing at all about whether the thing is useful. A tool worth adopting has
to give someone a reason to arrive on their own, and this one does not have that
reason yet — which is a fact about the tool, not about the channel.

This closes the question rather than parking it: nothing here is pending
authorization, and the absence of an external attempt is no longer to be reported
as something waiting to happen.

## Authority boundaries

An agent working this campaign may research, branch, implement, test, and prepare
commits, PR descriptions, and outreach drafts. It stops before: pushing, opening
or merging a pull request, releasing or publishing, uploading to a transparency
log, contacting anyone outside, and changing the visibility or naming of the
Kherson candidate. Each of those needs its own explicit authorization.

## Schedule

| Window | Work |
| --- | --- |
| 22–29 Aug | this manifest; Warrant public-surface cleanup; bake-off preregistration; a proposed decision on the Kherson candidate |
| 30 Aug – 12 Sep | local DSSE bridge; both bake-off implementations; negative controls; recorded results |
| 13–19 Sep | external handoff packets; shortlist; after authorization, publication and invitations |
| 20 Sep – 3 Oct | supporting outside participants; fixing reproduced blockers; no new infrastructure; final decision record |

## Decision, 2026-10-03

- **Warrant** continues if the vertical is one its own authors keep switched on,
  judged by the measures above. Independent outside use would settle the question
  faster and is still the only thing that counts as external signal — but the
  campaign no longer goes looking for it, so its absence is not a verdict.
- **Σ-GLYPH** remains the core runtime only on the bake-off result together with
  an externally relevant advantage; otherwise optional or frozen.
- **Decision Archaeology** continues only with a real external case.
- **OAIP** stays maintenance-only until a consumer exists.
- **BOS** stays frozen pending demand.
- **SEV** remains abandoned and outside the active member set unless a separate
  re-adoption act names a concrete consumer and current contracts.
- With no external signal, the outcome is a published honest retrospective and a
  freeze — not the next layer.

## Criteria change log

Criteria may be changed, but not quietly, and not after seeing a result they
would have decided.

| Date | What changed | Why | Result already known? |
| --- | --- | --- | --- |
| 2026-08-22 | initial statement | — | no |
| 2026-08-23 | final decision for Warrant restated to match the success criterion above; the two had disagreed since the outreach decision, one asking for independent use and the other for a workflow its authors keep | a criterion that contradicts its own decision rule decides nothing | no |
| 2026-08-23 | outreach cancelled as a line of work; Warrant's criterion moved from "an outside person installs it" to "one vertical its authors keep switched on"; Decision Archaeology frozen; bake-off budget raised to 40% and named a kill test | a cold message measures the sender's reach rather than the artifact, and no external attempt had been made under the old plan either | no |
| 2026-09-02 | SEV moved from frozen research to `ABANDONED`; the ecosystem map retains it as historical provenance | its enabling Warrant receipt direction had closed, no OAIP/BOS receipt composition or consumer materialized, and the terminal refund slice closed `NOT YET USEFUL`; the broader loss/semantic-hygiene obligation continues in manifesto without claiming format compatibility | yes — this is a disposition based on the recorded outcome, not a prospective success criterion |

## The metric this campaign is judged by

Not closed issues and not green gates: **an act by someone else that the
ecosystem made possible without its authors.** If there is none, the response is
to make the system smaller, not to strengthen its self-authored proof of its own
value.
