# Retirement record: protocol-ecosystem

## Disposition

```text
status: ARCHIVED
decision_date: 2026-09-02
mode: FUNCTION_DECOMPOSED
last_active_snapshot: f819c05bf12a7cdd52176a8bc899351b453154d3
```

`protocol-ecosystem` is retired as an active coordination and documentation
surface. This is not a claim that its history was useless or that every former
statement was false. It is a decision that the repository no longer has a
distinct live responsibility worth maintaining.

## Why the active surface ended

The repository described itself as an attributed map that owned no semantics,
governed no member, and was not consumed by any member repository. Its current
claims therefore had to be copied from independent owners and periodically
rechecked by hand.

That arrangement created the failure mode the map was intended to prevent:
stale cross-repository claims could remain visible after the owning repository
had changed. A freshness date and URL checks detected some decay but could not
establish that the copied semantic, implementation, governance, and release
states still formed the relation described by a row.

The active function is therefore decomposed instead of transferred whole.

## Successor mapping

| Responsibility | Canonical boundary after retirement |
|---|---|
| evaluator meaning and conformance | Σ-GLYPH owns its released profiles, bytes, vectors, and implementation evidence |
| consumer selection and composition | Warrant owns which exact evaluator it selects for a tag and the bounded evidence for that selection |
| semantic-credit discipline | Manifesto owns the vocabulary and mechanisms for claim scope, non-transitive credit, evolution, and controlled forgetting |
| repository status and adoption | each repository owns its own status and explicit owner acts |
| cross-repository view | generated observation over exact owner-published records; it is not an authority and must fail closed when stale |

The Warrant–Σ-GLYPH relation remains real where one repository consumes the
other. It must be represented by direct versioned contracts and conformance
evidence at those owners, not by a third repository's prose row. Manifesto may
describe or check the epistemic boundary of such a relation; it does not become
the runtime mediator or governing authority of either project.

## Preserved value

- the final relationship vocabulary and attributed map as a dated snapshot;
- the design thesis separating re-executability from persuasion;
- the record that absence of coupling can itself be useful information;
- the SEV archive and provenance-proto lineage acts;
- the external-pressure campaign as a historical decision record.

All preserved material remains reachable through Git. Preservation supplies
provenance, not current status.

## Known loss

After retirement there is no manually curated, human-readable global table of
the portfolio's current relations. A reader must inspect the canonical owner of
each relevant contract, or a generated projection that names exact owner
records.

This loss is intentional. The convenience of one table did not justify an
additional semantic surface whose agreement with all owners could not be
established by its own checks.

## What this act does not claim

- It does not dissolve direct dependencies or conformance obligations between
  repositories.
- It does not make Manifesto the owner of Warrant or Σ-GLYPH semantics.
- It does not certify the final map snapshot as complete or currently true.
- It does not delete Git history or the historical retirement records.
- It does not forbid a future generated portfolio view.

## Reactivation rule

The old manually maintained map must not be reactivated. A new integration
surface requires all of the following:

1. a named consumer and a concrete operation unavailable from owner-local
   records;
2. exact source revisions or released identities;
3. one canonical owner for every exported field;
4. explicit mapping, loss, freshness, and conflict semantics;
5. a generated projection that is inert when its source closure is stale; and
6. an executable counterexample showing that direct bilateral contracts are
   insufficient.

Without those operands, Git history is the appropriate ecosystem memory.

