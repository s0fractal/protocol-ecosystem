# SEV GitHub archive act — 2026-09-02

This records the platform transition separately from the repository retirement
decision. It is an attributed readback, not a cryptographic receipt and not a
claim that GitHub will preserve the repository forever.

## Subject

| Field | Value |
|---|---|
| GitHub repository | `s0fractal/sev` |
| GitHub repository node | `R_kgDOT0A75Q` |
| default branch | `master` |
| retirement merge | `6886d0f329e233b6866dcff3c19c6067f4e013b3` (PR #8) |
| retirement source commit | `5b199de24a17e0f273dc96d62c98904797e7cf77` |
| disposition | `ABANDONED`; never adopted; no replacement asserted |

## Transition and readback

After the retirement change reached the default branch and its `model` workflow
completed successfully, the owner authorized a separate GitHub archive act.
Repository metadata was first changed to:

- description: `ABANDONED historical research; never adopted. See
  RETIREMENT.md. Active stack: Sigma-Glyph, Warrant, Manifesto.`
- homepage: `https://github.com/s0fractal/protocol-ecosystem`

GitHub's repository API was read back at `2026-09-02T11:50:39Z` with:

```json
{
  "archived": true,
  "default_branch": "master",
  "full_name": "s0fractal/sev",
  "homepage": "https://github.com/s0fractal/protocol-ecosystem",
  "updated_at": "2026-09-02T11:50:39Z"
}
```

The public raw `master/README.md` was also read back after the act and began
with the `ABANDONED` status envelope plus links to Σ-GLYPH, Warrant, Manifesto,
and OAIP. Those projects are active directions by responsibility, not a claim
that they compose into or replace SEV.

## Boundary

- GitHub archive status is reversible platform state, not deletion.
- This record proves neither the identity of a future API respondent nor
  permanent recoverability. Git objects and the public remote remain
  best-effort preservation paths.
- Unarchiving the repository would not re-adopt SEV. Re-adoption requires the
  explicit conditions in SEV `RETIREMENT.md` and a corresponding active-map
  change.
- The archive act changes availability for contribution, not the truth status
  of any historical SEV claim.
