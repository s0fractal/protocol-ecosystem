# External-pressure campaign — decision date 2026-10-03

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
| Warrant — interoperability and outside use | active | 50% | ≤2 substantive PRs; ≤1 internal review/fix cycle before handoff |
| Σ-GLYPH / WASM bake-off | active | 25% | preregistration merged before any implementation |
| Decision Archaeology — one external case | active | 20% | intake and admission gate before any work |
| Ecosystem map and technical hygiene | active | 5% | documentation defects only |
| OAIP | maintenance-only | — | security, CI, compatibility, false documentation |
| BOS, SEV | **frozen pending external demand** | 0% | security, broken CI, critical dependencies, false documentation |

BOS and SEV keep their existing `research` status in the map. Frozen is a
statement about this campaign's attention, not about their standing: `historical`
would mean superseded, and neither is.

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

## Success criteria

**Warrant.** At least one independent person installs the tool without
synchronous help, verifies or creates a real receipt, and returns a reproducible
result or defect. Stars, views, model reviews, and replies from the author do not
count.

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

- **Warrant** continues if there is independent use or a concrete outside pull.
- **Σ-GLYPH** remains the core runtime only on the bake-off result together with
  an externally relevant advantage; otherwise optional or frozen.
- **Decision Archaeology** continues only with a real external case.
- **OAIP** stays maintenance-only until a consumer exists.
- **BOS / SEV** stay frozen pending demand.
- With no external signal, the outcome is a published honest retrospective and a
  freeze — not the next layer.

## Criteria change log

Criteria may be changed, but not quietly, and not after seeing a result they
would have decided.

| Date | What changed | Why | Result already known? |
| --- | --- | --- | --- |
| 2026-08-22 | initial statement | — | no |

## The metric this campaign is judged by

Not closed issues and not green gates: **an act by someone else that the
ecosystem made possible without its authors.** If there is none, the response is
to make the system smaller, not to strengthen its self-authored proof of its own
value.
