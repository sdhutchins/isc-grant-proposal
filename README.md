# ISC proposal: tidyvar, one variant table for R

A proposal to the R Consortium Infrastructure Steering Committee (ISC), 2026 round 2. It asks for 10,000 USD over eight months to build tidyvar, an R package that gives germline variant tables one shape and one identity:

- A variant table built on tibble that converts to and from the VRanges class in VariantAnnotation.
- GA4GH Variation Representation Specification (VRS) 2.0 identifiers, so variants join exactly across ClinVar, gnomAD, VEP output and local files. No R implementation of VRS exists today.
- Adapters that annotate the table from ClinVar, gnomAD, Ensembl VEP, MyVariant.info, UniProt and local files, with provenance (source, release, retrieval time, query) on every column.

Lead: Shaurita D. Hutchins, Center for Computational Genomics and Data Science, University of Alabama at Birmingham. Contributor: Samuel Bharti.

The source is `isc-proposal.qmd` and the files under `proposal/`. Rendered files are not tracked. Render locally (see Rendering) or download the `isc-proposal` artifact from the latest run of the render workflow under Actions.

## Deadline and submission

The round closes on 1 October 2026 at 11:59 pm US Eastern. The ISC notifies applicants on 1 November 2026, with acceptance due 1 December 2026. If the round is missed, the next one opens on 1 April 2027.

1. Make sure that every item under Open items is done.
2. Render the PDF (see Rendering) and read it once. It must stay within 5 pages.
3. Submit the PDF through the form linked from <https://r-consortium.org/all-projects/callforproposals.html> (forms.gle/o1nhNrdzebQc2DNU6).
4. Keep the thank-you message and the confirmation email.

## Open items

- `proposal/01-signatories.qmd`: add one line of the lead's public work with links.
- `proposal/01-signatories.qmd`: fill the Consulted section with people who replied, or delete it. A note of support from the Worthey lab is the most useful one to get.
- `proposal/04-timeline.qmd`: confirm the hours (200) and the rate (50 USD per hour).
- The working package name is `tidyvar`. It was free on CRAN on 1 October 2026. A GitHub repository named tidyvars (vector autoregression models) exists. The fallback name is `tidyvariants`.
- After submission, before any review call: compute one VRS identifier in R and show it matches the `VRS_Allele_IDs` field in a gnomAD v4 VCF. Put the snippet in this repository.

## Rendering

You need Quarto 1.4 or later and a LaTeX install. `quarto install tinytex` gives you one.

```sh
quarto render isc-proposal.qmd --to hikmah-pdf
quarto render isc-proposal.qmd --to html
```

Two GitHub Actions workflows run on push to `main`. `render-proposal.yaml` renders the PDF and the HTML and attaches them to the run as an artifact named `isc-proposal`. `publish-proposal.yaml`, from the template, publishes the HTML to GitHub Pages once someone has run `quarto publish gh-pages isc-proposal.qmd` from a local checkout.

## Layout

| Path | Content |
|---|---|
| `isc-proposal.qmd` | Title block and the list of included sections |
| `proposal/00-exec-summary.qmd` | Executive summary |
| `proposal/01-signatories.qmd` | Project team, contributors and consulted people |
| `proposal/02-problemdefinition.qmd` | The problem and the three gaps |
| `proposal/03-proposal.qmd` | Overview, minimum viable product, architecture, assumptions, dependencies |
| `proposal/04-timeline.qmd` | Start-up, milestones, failure modes, dissemination, budget |
| `proposal/05-success.qmd` | Definition of done, measures, future work |
| `references.bib` | Citations |
| `_extensions/` | The hikmah PDF format from the official ISC template |

The template is the official one from <https://github.com/RConsortium/isc-proposal>. The ISC asks for 2 to 5 pages and 500 to 2,500 words, written in the applicant's own voice. The earlier tutorial index proposal is in the history of this repository (pull request 1).
