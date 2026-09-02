# protocol-ecosystem — archived

**Disposition:** `ARCHIVED`

**Retirement decision:** 2026-09-02

**Last active map snapshot:**
[`f819c05`](https://github.com/s0fractal/protocol-ecosystem/tree/f819c05bf12a7cdd52176a8bc899351b453154d3)

This repository no longer maintains a current ecosystem map, coordinates the
repositories it once listed, or carries current compatibility and adoption
claims. Its manually maintained map had become an additional stale semantic
surface even though it owned no protocol contract and no member depended on it.

The repository remains available as historical provenance. The retirement
reasoning, successor boundaries, preserved value, losses, and reactivation rule
are recorded in [`RETIREMENT.md`](RETIREMENT.md).

## Successor boundaries

| Former concern | Current owner or location |
|---|---|
| deterministic evaluator semantics, identities, and conformance | the relevant Σ-GLYPH release and repository |
| selection of a Σ-GLYPH evaluator by Warrant | the relevant Warrant release, tag mapping, and consumer-side conformance gate |
| semantic hygiene, credit boundaries, concept evolution, and controlled forgetting | Manifesto |
| a repository's status, adoption, release, and public contract | that repository itself |
| portfolio navigation | a generated, non-authoritative projection of owner-published records, if one is needed |

No successor inherits the old map's statements merely by being named here.
Cross-repository compatibility exists only where a consumer names exact
provider bytes or a released identity and a bounded check verifies the claimed
relation.

## Historical material

- The final active relationship map and design thesis remain in
  [`README.md@f819c05`](https://github.com/s0fractal/protocol-ecosystem/blob/f819c05bf12a7cdd52176a8bc899351b453154d3/README.md).
- [`CAMPAIGN.md`](CAMPAIGN.md) is a frozen coordination record, not a current
  plan.
- [`retirements/`](retirements/) preserves the SEV archive act and the
  provenance-proto retirement record.

## Reactivation boundary

Do not resume a manually maintained global status map. A successor may be
proposed only for a named consumer that cannot obtain the required relation from
owner-published machine-readable records. It must define bounded inputs,
canonical ownership, freshness semantics, loss, and a falsifier before any
current status is published.
