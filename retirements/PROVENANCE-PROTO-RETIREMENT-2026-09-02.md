# `provenance-proto` retirement — 2026-09-02

This record retires a local pre-repository scratch directory after identifying
its promoted successor. It preserves lineage, not the source bytes themselves,
and grants no current protocol or validation status.

## Subject

| Field | Value |
|---|---|
| local directory | `~/Projects/provenance-proto` |
| repository | none; the directory was never initialized as Git |
| disposition | `SUPERSEDED`; remove from the active workspace surface |
| successor | OAIP initial commit `00dd75abf41a4aff89920dbc09fd0c1498290282` |
| successor date | `2026-07-18T14:32:32+03:00` |

The directory contained exactly two regular files when inspected:

| File | Size | Local birth and modification time | SHA-256 | Git blob ID |
|---|---:|---|---|---|
| `README.md` | 3,789 bytes | `2026-07-18T14:10:11+03:00` | `3a69ec23e9cebd3db4f15f5203c1fe3f492fa936c603011f03bca91e05ddc7c0` | `b6e4d7402d7b7f3a2ebddd5af8124ed755bc6c99` |
| `oaip.py` | 14,124 bytes | `2026-07-18T14:08:16+03:00` | `5d2307dc6d1e14f1c6d4866a62dd5cba7c154feeabe4e33c4f7ce9de1e9db97e` | `e6584fd4b85b985dbd4b035cbac6900bc7709f49` |

Neither exact blob was present in the OAIP Git object database at inspection
time. The identifiers above therefore bind the inspected local bytes but do
not claim that a public remote can recover them.

## Why it existed

The scratch README called itself an “OAIP prototype” and posed a deliberately
pre-repository question: whether a provenance ledger plus a claim-to-Warrant
bridge would prove useful in real agent-development work. It implemented a
minimal Observer, Ledger, and Bridge and stated the design boundaries that OAIP
later adopted:

- workspace state is a full snapshot, not merely `HEAD`;
- execution success is not claim validation or acceptance;
- SQLite is a deletable projection over content-addressed records;
- effects and attribution uncertainty are explicit;
- accepted claims become Warrant records.

The prototype earned its repository. OAIP's initial commit followed 22 minutes
after the two local files were created, and the live OAIP specification and
implementation now own those concepts.

## Successor comparison

Comparing the scratch `oaip.py` with `impl/oaip.py` at OAIP's initial commit
produced an 8-line addition and 1-line removal. The only implementation change
made the Warrant command configurable through `WARRANT_CLI`, retaining the
sibling-checkout path as a fallback instead of making it unconditional. No
independent implementation branch or distinct protocol surface was found.

The scratch README was expanded and rewritten during promotion. Its substantive
design commitments are represented in OAIP's current README and specification;
the exact pre-repository wording is not canonical.

## Retirement boundary and accepted loss

- No repository in the inspected workspace refers to the local directory as a
  dependency or executable input. This ecosystem map was its only explicit
  lineage reference.
- Removing the directory removes no active runtime, gate, normative surface, or
  unique design obligation.
- The accepted loss is the recoverability of the exact two pre-repository file
  bodies from this repository. Their hashes are identity commitments, not a
  backup. OAIP's initial commit preserves the implementation with the small
  configuration repair described above, while OAIP's current documents preserve
  the surviving concepts.
- Recreating a directory with these names would not revive this artifact. A new
  experiment must receive a new identity and state its relation to OAIP.
- This is controlled forgetting by supersession: the live working surface is
  reduced while the reason, successor, comparison, and known loss remain
  addressable.
