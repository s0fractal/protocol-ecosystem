# Ecosystem relationship map

> `protocol-ecosystem` is **not** a source of truth for semantics and **not** a
> governing body. It is an attributed map of relations between independent
> protocols — the ones that exist and are gated, the ones that are proposed,
> and the ones that are conspicuously absent. Member repositories never depend
> on this repository: no submodule, no pin, no CI coupling. A plain URL link
> in a member README is the maximum permitted inbound reference.

```
member repositories
      │
      │  public contracts, releases, CI receipts
      ▼
protocol-ecosystem          ← indexes and explains relations; owns nothing
```

Every claim in the table cites where it is checked. A row without a gate
cannot carry a `normative` or `verified-compatible` status — that rule exists
so a reader (human or model) cannot confuse "we imagine BOS↔OAIP" with "this
contract exists and CI enforces it".

## Shared design thesis: re-executability over persuasion, where possible

When a claim can honestly be reduced to a bounded mechanical procedure, this
ecosystem prefers an artifact that lets another party reproduce the path from
pinned bytes to a verdict over prose asking that party to accept the author's
conclusion. Persuasion is a relation between a speaker and an audience;
re-executability is a property of an artifact. The reader's agreement is not an
input to the latter — their machine can perform the declared check again.

This does **not** eliminate trust, prove truth, or automate judgment. It moves
the irreducible trust boundary into the open:

- whether the declared check represents the question people actually care
  about;
- whether its inputs, provenance, and claimed authority should be accepted;
- whether the pinned runtime, profile, and implementation assumptions are
  adequate; and
- what was omitted, unavailable, or deliberately left outside the check.

The protocols contribute different parts of that separation without collapsing
them into one verdict. **The table below is a design thesis, not a status
table.** It says what each surface is *for* in this separation; the standing
column says how much of it exists today, in the same terms the Members table
uses. Nothing here upgrades a relation status, and a surface marked *research*
describes an intent rather than a contract anyone can currently re-execute.

| Surface | Standing | What becomes replayable or explicit | What does not follow |
|---|---|---|---|
| **OAIP** | adopted | the observed execution and its content-addressed record | that execution was validated or accepted |
| **Warrant** | adopted | the named authority, policy bytes, and bounded executable reason | that a signature makes the claim true or the policy appropriate |
| **Σ-GLYPH** | adopted | deterministic evaluation of the same canonical term under the same ATP budget | that the term expresses the right real-world question — nor, per `DA-SIGMA-0001`, that any published encoding turns outside bytes into that term |
| **BOS** | research, not adopted | attribution and observer-relative assessments in a decision graph | one observer-independent meaning or final truth |
| **SEV** | historical — `ABANDONED` 2026-09-02 | a snapshot-bound projection together with an explicit account of loss | that the projection is complete merely because it verifies; no replacement implements the SEV format |
| **Decision Archaeology** | application driver, not a member protocol | replay of formal facts and procedures preserved by a case | guilt, legality, intent, or the final interpretation of the case |

The compact form is: **re-executability does not replace persuasion; it narrows
persuasion's jurisdiction to an explicit semantic and trust boundary.** When a
question cannot be reduced without pretending that judgment is computation, the
honest artifact preserves the claim, competing interpretations, and the unknown
instead of manufacturing an executable verdict.

## Members

| Repo | One line | Public location | Visibility |
|---|---|---|---|
| **Σ-GLYPH** (`sigma-glyph`) | content-addressed, ATP-bounded, Lean-proven deterministic evaluation; hash is identity | github.com/s0fractal/sigma-glyph | public |
| **Warrant** (`warrant`) | signed authority records: who was allowed to decide what, under which policy, with re-executable reasons | github.com/s0fractal/warrant | public |
| **OAIP** (`oaip`) | Observed Action & Intent Protocol: content-addressed observation of what was actually done; *execution ≠ validation ≠ acceptance* | github.com/s0fractal/oaip | public |
| **BOS** | typed decision graph with observer-relative assessments; source of attribution, not of meaning | github.com/s0fractal/BOS (research, not adopted) | public |

## Historical and abandoned trajectories

These repositories remain available as provenance but are excluded from the
default active member set. Historical availability is not re-adoption.

| Repo | Disposition | Preserved value | Reactivation boundary |
|---|---|---|---|
| **SEV** ([archived repository](https://github.com/s0fractal/sev)) | `ABANDONED` by owner decision and GitHub-archived on 2026-09-02; never adopted | sealed snapshot byte-core, projection-scoped `loss_manifest`, and the failed refund-slice controls | a new proposal must name a concrete consumer and current owner-defined contracts; [`RETIREMENT.md@5b199de`](https://github.com/s0fractal/sev/blob/5b199de24a17e0f273dc96d62c98904797e7cf77/RETIREMENT.md) is the exact status envelope and [`SEV-ARCHIVE-ACT-2026-09-02.md`](retirements/SEV-ARCHIVE-ACT-2026-09-02.md) records the separate platform act |

## Application drivers (non-normative)

Application drivers are real consumers of the stack, not member protocols and
not governance authorities. They turn concrete use into bounded integration
demand: a blocked operation, its inputs, a minimal reproducer, the expected
failure mode, and a conformance vector. They do not own protocol semantics and
cannot upgrade a relation status by filing a feature request.

| Repo | Ecosystem role | Authority boundary | Evidence | Visibility |
|---|---|---|---|---|
| **Decision Archaeology** (`decision-archaeology`) | case-driven demand driver and reference consumer for reproducible retrospective investigations | owns investigation workflow and local presentation/storage models only; OAIP, Warrant, Σ-GLYPH, and BOS retain their existing contract ownership. Historical SEV references carry no live contract authority | [github.com/s0fractal/decision-archaeology](https://github.com/s0fractal/decision-archaeology); [`main@1657954`](https://github.com/s0fractal/decision-archaeology/commit/1657954ea4142842254623819c3a6b066ac46f91) contains the first executable case, `needs@v0`, and the first fulfilled cross-repository outcome | public |

Here, **driver** means empirical demand driver, not dependency root, semantic
source of truth, release coordinator, or governing body. Member repositories
must not depend on Decision Archaeology. A case may discover a protocol need,
but only the canonical owner can define and release the corresponding contract.

In legal or policy-facing work, this boundary is especially strict. A case may
replay that preserved bytes have a particular identity, that an arithmetic
relation holds, or that a declared formal procedure evaluates a certain way. It
must not promote those results into a finding of corruption, guilt, legality,
good faith, or public interest. Those are interpretive claims and remain
attributed, contestable, and subject to the authority competent to decide them.

```text
real case
   │
   ▼
test the existing contract through a local adapter/profile
   │  still blocked: minimal reproducer + counter-vector
   ▼
canonical contract owner disposition
   ├── already supported / application adapter → case owner implements and pins
   └── protocol candidate → owner proposal, conformance gate, and release
   │
   ▼
case replay + outcome receipt linking both exact revisions
```

The adapter/profile step is deliberately first. A protocol feature request is
justified only when the current owner cannot express the required behaviour
without changing its public contract.

## Coordination (non-normative)

[`CAMPAIGN.md`](CAMPAIGN.md) records the current external-pressure campaign: what
is active, what is frozen, and what decides each stream. It is a coordination
plan and **must not be cited as a gate** — no row in the table below may draw its
status from it, and no member repository depends on it. The file deliberately
carries no date in its name. The staleness check reads only the dedicated
map-wide review marker at the end of this file; a newer bounded row update or a
campaign date cannot silently refresh unrelated status claims.

## Relation statuses (closed set)

| Status | Meaning |
|---|---|
| `normative` | a written contract one side MUST satisfy, enforced by a named CI gate |
| `verified-compatible` | no normative dependency, but a gate demonstrates the surfaces currently agree |
| `proposed` | a written proposal/ADR exists; no implementation or gate |
| `intended` | stated intention in prose only; nothing written as a contract |
| `research` | drafts/experiments; expected to change without notice |
| `historical` | removed from the live relation surface and kept as provenance; the row must state whether the cause was supersession, abandonment, or another retirement mode |

## Relations

| From | To | Relation | Consumed surface | Status | Evidence / gate |
|---|---|---|---|---|---|
| Warrant | Σ-GLYPH | `ski@v1` reason runtime | Book I (canonical bytes, 4-opcode evaluator, 49 conformance vectors) | `normative` | `warrant-go` sigma-conformance; sigma CI replays Book I across 4 engines |
| Σ-GLYPH | Warrant | release adoption + governance gate | `warrant verify --store-mode`, threshold warrants over anchor-set blobs, out-of-band trust config | `normative` | sigma `ci.yml` (`WARRANT_PIN`, `anchor_governance.py status --enforce`); `tools/x1_cross_repo.sh` HEAD-vs-HEAD with negative controls |
| OAIP | Warrant | claim → acceptance bridge | Warrant body schema, JCS canonicalization ("exactly per Warrant SPEC §4"), verify CLI, trust-config shape | `normative` | OAIP CI pins warrant commit `8508a4a`; bridge refusal for `verdict != pass` is tested. Known deficit: the reference impl files checks as prose+evidence, not machine-readable check reasons (OAIP SPEC §3) |
| OAIP | Σ-GLYPH | `ski@v1` validation runtime | reserved identifier only — claim 0.1 MUST reject it | `proposed` | reject vector in `oaip/examples/record-vectors.json` (the gate enforces the *absence*) |
| BOS | Warrant | authority / adoption carrier | none yet (`warrant` is a valid `scope` label and `context_cut.anchors.kind`; zero `adoption`/`decision` atoms exist; genesis key unpinned) | `proposed` | no gate; BOS Phase 3 exit criterion |
| BOS | Σ-GLYPH | deterministic subclaim replay | none yet | `intended` | no gate; BOS Phase 4 exit criterion |
| BOS | OAIP | action/experience context | **none — zero mentions in either direction as of 2026-08-09** | `intended` | no gate; the historical SEV drafts were the first artifact to even name both |
| BOS | [Trinity](https://github.com/s0fractal/trinity) | general cognitive/process substrate | none (`trinity` scope label; "must not fork a second journal before E0001") | `intended` | no gate. *Row corrected 2026-09-02: it previously said "local-only: no public repo"; trinity has had a public origin (`github.com/s0fractal/trinity`) throughout — the claim was about the author's workspace, not the surface.* |
| SEV | Warrant + OAIP + BOS + Σ-GLYPH | historical PROV Evidence View projection | the anticipated SEV receipt composition did not become a cross-repository contract: Warrant closed WRT-003 in favour of a Warrant-owned report, the OAIP/BOS receipt surfaces did not exist, and no consumer adopted the projection | `historical` | SEV public surface `master@33a08a6`; terminal negative slice `author/vertical-slice-refund@4453bf3`; Warrant closure `25bd44c`; retirement record `5b199de`, landed as `master@6886d0f`; [GitHub archive act](retirements/SEV-ARCHIVE-ACT-2026-09-02.md). This row preserves provenance and grants no current status |
| Decision Archaeology *(application)* | OAIP + Warrant + Σ-GLYPH + BOS | case-driven integration feedback loop | `case@v0` dossiers route blocked operations through evidence-bound `need@v0` packets and close them with `need-outcome@v0`; the general bridges remain local/research and each canonical owner retains authority. Its SEV field notes and constraint-cache witness are historical analysis under a retirement envelope, not a live integration | `research` | [`main@1657954`](https://github.com/s0fractal/decision-archaeology/commit/1657954ea4142842254623819c3a6b066ac46f91); [case-derived needs loop](https://github.com/s0fractal/decision-archaeology/blob/1657954ea4142842254623819c3a6b066ac46f91/docs/case-derived-needs.md); [first outcome](https://github.com/s0fractal/decision-archaeology/blob/1657954ea4142842254623819c3a6b066ac46f91/outcomes/DA-SIGMA-0001.json); [SEV consumer status envelope `efba9a8`](https://github.com/s0fractal/decision-archaeology/commit/efba9a8b0959e34f277c8078c43ee02efecd4f6d) |
| Decision Archaeology *(application)* | Σ-GLYPH | claim-bound exact-sum replay profile | application-owned `sigma-money-add-eq@v0` consumes published `sigma-glyph==0.6.7` Book I bytes, C1, and bounded evaluation; compatibility is for that exact pin and does not add the profile to the Σ-GLYPH standard | `verified-compatible` | DA [`main@1657954`](https://github.com/s0fractal/decision-archaeology/commit/1657954ea4142842254623819c3a6b066ac46f91): 4 frozen vectors + barite case 9/9 + outcome receipt; Σ-GLYPH [`master@01069d0`](https://github.com/s0fractal/sigma-glyph/commit/01069d0410e6fc3b37d5dfeea1c58939e7ff6350): owner-classified `application-adapter`, packet `fulfilled` |
| mind-os | Warrant | decision graduation demo | mind-os public JSON projection → warrant `accept`; no hard dependency either way | `research` | `oaip/examples/graduate-decision.sh` (a demo, not a gate) |
| provenance-proto *(local-only: no public repo)* | OAIP | ancestor scratch prototype (2026-07-18) | superseded entirely; the local directory may be removed from the active workspace | `historical` | OAIP initial commit `00dd75a`; [retirement and lineage record](retirements/PROVENANCE-PROTO-RETIREMENT-2026-09-02.md). No runtime dependency or current protocol status |
| Semantica *(external)* | SEV | historical possible-consumer note | SEV canonical N-Quads dataset | `historical` | no integration ever existed; retained only to show the consumer hypothesis that did not materialize |

## Local paths (non-normative convenience)

A conventional developer workspace, **not** part of any protocol; another
machine has another home directory and none of the contracts above may
reference these paths:

```
Default workspace: ~/Projects

warrant      → ~/Projects/warrant
oaip         → ~/Projects/oaip
BOS          → ~/Projects/BOS
sigma-glyph  → ~/Projects/sigma-glyph
sev          → ~/Projects/sev  (historical, ABANDONED; not in active set)
decision-archaeology → ~/Projects/decision-archaeology
trinity      → ~/trinity
```

## Rules of this map

1. **No submodules, ever, in either direction.** A submodule pin shows a
   snapshot but proves no compatibility, and every map edit would ripple
   pointer bumps through independent repositories (the sibling-pin ping-pong
   this ecosystem has already lived through).
2. **Member repos may link here by URL only** — no git pin, no CI dependency.
3. **Every row cites its gate.** Editing a status upward (`intended` →
   `proposed` → `normative`) requires naming the artifact that justifies it;
   a green suite that covers less than the row claims is the known failure
   mode this column exists to catch.
4. **Rows for absences are first-class.** "Zero coupling" is information; its
   removal requires the coupling to actually appear.
5. **Attribution over resolution.** Where members disagree about a relation,
   this file records both positions with authors and dates; it does not pick
   a winner.
6. If a single-checkout integration surface is ever needed, this repo may
   *unilaterally* add a clone script or an `integration-lock.json`
   (release URL + commit + artifact digest) and run pinned-compatibility and
   HEAD-to-HEAD gates. Member repos still never include this one back.
7. **Feature pressure is not protocol authority.** An application driver may
   publish a failing vector or request, but the canonical owner decides whether
   the need is already expressible, belongs in a narrow adapter/profile, or
   requires a protocol change. This map records adoption only after an exact
   released identity and owner-side gate exist.

---

*Map-wide status review: 2026-08-09. SEV and provenance-proto received bounded
retirement updates on 2026-09-02, and the BOS→Trinity row's stale "no public repo" note was
corrected the same day; those updates do not refresh unrelated rows. The Decision
Archaeology rows were checked 2026-08-21 at
`main@1657954` against Σ-GLYPH `master@01069d0`. Statuses decay; a dated row that was never
re-checked is a `historical` claim about that date, not a current fact.*
