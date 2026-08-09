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

## Members

| Repo | One line | Public location |
|---|---|---|
| **Σ-GLYPH** (`sigma-glyph`) | content-addressed, ATP-bounded, Lean-proven deterministic evaluation; hash is identity | github.com/s0fractal/sigma-glyph |
| **Warrant** (`warrant`) | signed authority records: who was allowed to decide what, under which policy, with re-executable reasons | github.com/s0fractal/warrant |
| **OAIP** (`oaip`) | Observed Action & Intent Protocol: content-addressed observation of what was actually done; *execution ≠ validation ≠ acceptance* | github.com/s0fractal/oaip |
| **BOS** | typed decision graph with observer-relative assessments; source of attribution, not of meaning | github.com/s0fractal/BOS (research, not adopted) |
| **SEV** | PROV Evidence View: loss-aware projection of verified receipts into canonical RDF | (research drafts, no repo yet) |

## Relation statuses (closed set)

| Status | Meaning |
|---|---|
| `normative` | a written contract one side MUST satisfy, enforced by a named CI gate |
| `verified-compatible` | no normative dependency, but a gate demonstrates the surfaces currently agree |
| `proposed` | a written proposal/ADR exists; no implementation or gate |
| `intended` | stated intention in prose only; nothing written as a contract |
| `research` | drafts/experiments; expected to change without notice |
| `historical` | superseded; kept as provenance, not as a live surface |

## Relations

| From | To | Relation | Consumed surface | Status | Evidence / gate |
|---|---|---|---|---|---|
| Warrant | Σ-GLYPH | `ski@v1` reason runtime | Book I (canonical bytes, 4-opcode evaluator, 49 conformance vectors) | `normative` | `warrant-go` sigma-conformance; sigma CI replays Book I across 4 engines |
| Σ-GLYPH | Warrant | release adoption + governance gate | `warrant verify --store-mode`, threshold warrants over anchor-set blobs, out-of-band trust config | `normative` | sigma `ci.yml` (`WARRANT_PIN`, `anchor_governance.py status --enforce`); `tools/x1_cross_repo.sh` HEAD-vs-HEAD with negative controls |
| OAIP | Warrant | claim → acceptance bridge | Warrant body schema, JCS canonicalization ("exactly per Warrant SPEC §4"), verify CLI, trust-config shape | `normative` | OAIP CI pins warrant commit `8508a4a`; bridge refusal for `verdict != pass` is tested. Known deficit: the reference impl files checks as prose+evidence, not machine-readable check reasons (OAIP SPEC §3) |
| OAIP | Σ-GLYPH | `ski@v1` validation runtime | reserved identifier only — claim 0.1 MUST reject it | `proposed` | reject vector in `oaip/examples/record-vectors.json` (the gate enforces the *absence*) |
| BOS | Warrant | authority / adoption carrier | none yet (`warrant` is a valid `scope` label and `context_cut.anchors.kind`; zero `adoption`/`decision` atoms exist; genesis key unpinned) | `proposed` | no gate; BOS Phase 3 exit criterion |
| BOS | Σ-GLYPH | deterministic subclaim replay | none yet | `intended` | no gate; BOS Phase 4 exit criterion |
| BOS | OAIP | action/experience context | **none — zero mentions in either direction as of 2026-08-09** | `intended` | no gate; the SEV drafts are the first artifact to even name both |
| BOS | Trinity | general cognitive/process substrate | none (`trinity` scope label; "must not fork a second journal before E0001") | `intended` | no gate |
| SEV | Warrant + OAIP + BOS + Σ-GLYPH | PROV Evidence View projection | a `warrant.verification-receipt@v0` contract that **does not exist yet** — SEV is explicitly blocked on it | `research` | drafts only (`specs/sev/`, unversioned); Codex review 2026-08-09: verdict AMEND, rev 2 applied |
| mind-os | Warrant | decision graduation demo | mind-os public JSON projection → warrant `accept`; no hard dependency either way | `research` | `oaip/examples/graduate-decision.sh` (a demo, not a gate) |
| provenance-proto | OAIP | ancestor scratch prototype (2026-07-18) | superseded entirely | `historical` | none; kept as provenance |
| Semantica *(external)* | SEV | possible PROV-O consumer | SEV canonical N-Quads dataset | `research` | no integration; semantica ships its own `export_prov()` — the differential value is *verified* vs *asserted* provenance |

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
sev drafts   → ~/Projects/specs/sev
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

---

*Snapshot date for all status claims: 2026-08-09. Statuses decay; a dated row
that was never re-checked is a `historical` claim about that date, not a
current fact.*
