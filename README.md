# ISC proposal: an index, template and validator for browser-run R tutorials

A proposal to the R Consortium Infrastructure Steering Committee (ISC), 2026 round 2. It asks for 10,000 USD over eight months to build three things:

- `tutorialindex`, a small R package with a metadata schema for tutorials, a validator, and a function that scaffolds a new tutorial.
- A template repository that publishes a quarto-live tutorial to GitHub Pages, with CRAN and Bioconductor packages loaded in the browser through r-universe.
- An open index site where any R tutorial can be listed by pull request and found by package, level and topic.

Three reference tutorials test the template: an introductory R lesson adapted from Software Carpentry, a DESeq2 companion to the Bioconductor bioc-rnaseq lesson, and package development with usethis and devtools.

The source is `isc-proposal.qmd` and the files under `proposal/`. Rendered files are not tracked. Render locally (see Rendering) or download the `isc-proposal` artifact from the latest run of the render workflow under Actions.

## Deadline and submission

The round closes on 1 October 2026 at 11:59 pm US Eastern. The ISC notifies applicants on 1 November 2026. If the round is missed, the next one opens on 1 April 2027.

1. Make sure that every item under Open items is done.
2. Render the PDF (see Rendering) and read it once. It must stay within 5 pages.
3. Submit the PDF through the form linked from <https://r-consortium.org/all-projects/callforproposals.html> (forms.gle/o1nhNrdzebQc2DNU6).
4. Keep the thank-you message and the confirmation email.

## Open items

- `proposal/01-signatories.qmd`: complete Shaurita's Project team entry (what she brings, links, hours).
- `proposal/01-signatories.qmd`: fill the Consulted section with people who replied, or delete the section. Do not list anyone who has not answered.
- `proposal/04-timeline.qmd`: confirm the hours (200) and the rate (50 USD per hour). If a second person is paid from the grant, change the milestone table so the total stays at or below 10,000 USD.
- The working package name is `tutorialindex`. It was free on CRAN on 26 September 2026. Change it in `proposal/03-proposal.qmd` and `proposal/05-success.qmd` if you pick another name.

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
| `proposal/01-signatories.qmd` | Project team and consulted people |
| `proposal/02-problemdefinition.qmd` | The problem and the three gaps |
| `proposal/03-proposal.qmd` | Overview, minimum viable product, architecture, assumptions, dependencies |
| `proposal/04-timeline.qmd` | Start-up, milestones, failure modes, dissemination, budget |
| `proposal/05-success.qmd` | Definition of done, measures, future work |
| `references.bib` | Citations |
| `_extensions/` | The hikmah PDF format from the official ISC template |

The template is the official one from <https://github.com/RConsortium/isc-proposal>. The ISC asks for 2 to 5 pages and 500 to 2,500 words, written in the applicants' own voice.
