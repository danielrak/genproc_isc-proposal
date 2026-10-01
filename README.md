# genproc: ISC grant proposal

[![build-status](https://github.com/danielrak/genproc_isc-proposal/actions/workflows/publish-proposal.yaml/badge.svg)](https://github.com/danielrak/genproc_isc-proposal/actions/workflows/publish-proposal.yaml)

Proposal to the [R Consortium ISC grant programme](https://r-consortium.org/all-projects/callforproposals.html),
round 2026-2, for the [`genproc`](https://github.com/danielrak/genproc) R package
(on CRAN since May 2026).

`genproc` turns a procedure written for one case into a run over many cases:
the user supplies a function and a mask (one row per case), and gets back one
object holding a per-case log with real tracebacks, a reproducibility snapshot
with input-file fingerprints, and helpers to re-run only what failed or
changed. Parallel, non-blocking and progress-monitoring layers compose on top.

The proposal asks for twelve months of work (January to December 2027) on five
milestones, 13 000 USD in total, all labour:

1. A written, versioned contract for iterated runs (model of the iterated process, error-tolerance and retry rules), published for review.
2. A backwards-compatible `genproc_mask` class implementing that contract.
3. The remaining execution layers: error replay, content-hash input fingerprints, live monitoring of non-blocking runs, cancellation.
4. Evaluation by outside users on documented failure-and-recovery tasks, and a worked `targets` integration.
5. A 1.0.0 release with a stable lifecycle, governance documents and a succession process.

## Files

- `isc-proposal.qmd`: master document; includes the six section files.
- `proposal/00-exec-summary.qmd` to `proposal/05-success.qmd`: the sections, in the order of the official template.
- `references.bib`: bibliography.
- `_quarto.yml`, `_extensions/`: Quarto project config and the `hikmah` PDF format used by the template.

The HTML comments inside the section files are the official template guidance
and do not appear in the rendered output.

## Build

```bash
quarto render isc-proposal.qmd
```

produces `isc-proposal.html` and `isc-proposal.pdf`. The PDF format needs a
LaTeX distribution (TinyTeX is enough). Pushes to `main` render and publish the
proposal to GitHub Pages through `.github/workflows/publish-proposal.yaml`, once
`quarto publish gh-pages isc-proposal.qmd` has been run interactively a first
time.

## Key dates (round 2026-2)

- Submission closes: 1 October 2026, 23:59 US ET (2 October, 05:59 Paris).
- Notification: 1 November 2026. Acceptance deadline: 1 December 2026.

## License

Based on the [ISC proposal boilerplate](https://github.com/RConsortium/isc-proposal)
by Stephanie Locke (CC BY 4.0). The proposal text is CC BY 4.0.
