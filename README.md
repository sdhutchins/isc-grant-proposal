# tutorialverse: Interoperability and quality infrastructure for R tutorials

A proposal to the R Consortium Infrastructure Steering Committee (ISC), led by Shaurita D. Hutchins in collaboration with Samuel Bharti. Both are PhD candidates at the University of Alabama at Birmingham.

tutorialverse provides shared metadata, validation, discovery, and review infrastructure so interactive R tutorials can be created with different tools while participating in one maintainable ecosystem.

The 12-month project will deliver a minimal metadata schema and an R validation package with adapters for `learnr`, `learnr2`, and Quarto Live. A registry will index externally maintained tutorials, including Carpentries-style materials, with a documented review and maintenance process. Each entry will state the checks performed; indexing alone will not imply that its exercises have been tested.

Existing engines will run the tutorials. Browser runtimes, new execution engines, and static-hosting infrastructure are outside the funded scope. Four small reference tutorials will test the adapters across different teaching contexts: `renv`, package development with `usethis` and `devtools`, `DESeq2`, and an introductory Carpentries R lesson.

The requested budget is **USD 10,000**, covering 200 hours at USD 50/hour across five milestones: 120 hours and USD 6,000 for Hutchins (60%), and 80 hours and USD 4,000 for Bharti (40%). The indexing pilot will cover 5–10 existing tutorials, and at least three external contributors will review the work during the grant.

## Preliminary work

The [tutorialverse prototype](https://github.com/tutorial-verse/tutorialverse) reads YAML metadata and returns structured validation results. Its local tests use synthetic records with learnr, learnr2, and Quarto Live identifiers. It does not contact tutorial URLs, render lessons, or execute exercises; adapters and real-tutorial indexing remain proposed work.

Public outreach is documented in `proposal/01-signatories.qmd`. An initial community response pointed to `learnr2` and Quarto Live; it does not establish maintainer support for a shared schema.

## Next steps

- Seek engine-maintainer and educator feedback on the minimal schema and supported checks.
- Align the prototype fields with the proposed schema: the prototype currently requires topics, while the proposal requires learning objectives and makes topics optional.
- Use the funded indexing pilot to test 5–10 existing tutorials and record missing metadata and author effort. Record exercise execution separately.
- Confirm the start date and package-name availability, and update the preliminary-work section and baseline counts as work is completed.

## Deadline and submission

The [ISC call for proposals](https://r-consortium.org/all-projects/callforproposals.html) lists the 2026 second-round deadline as 1 October 2026 at 11:59 pm US Eastern, with notification on 1 November 2026. The ISC requires a self-contained PDF of 2–5 pages using its template. Submit through the form linked from the official call and retain the confirmation message and email.

## Rendering

The source is `isc-proposal.qmd` and the six sections under `proposal/`. Rendered files are not tracked. You need Quarto 1.4.11 or later and a LaTeX installation; `quarto install tinytex` installs TinyTeX if needed.

```sh
quarto render isc-proposal.qmd --to hikmah-pdf
quarto render isc-proposal.qmd --to html
```

`render-proposal.yaml` renders PDF and HTML on pushes to `main` and pull requests, and attaches them as an artifact named `isc-proposal`. The existing `publish-proposal.yaml` workflow publishes HTML to GitHub Pages after initial local setup with `quarto publish gh-pages isc-proposal.qmd`.

## Layout

| Path | Content |
|---|---|
| `isc-proposal.qmd` | Title, both authors, and section includes |
| `proposal/00-exec-summary.qmd` | Executive summary |
| `proposal/01-signatories.qmd` | Responsibilities, public feedback, and planned consultation |
| `proposal/02-problemdefinition.qmd` | The interoperability problem and existing engines |
| `proposal/03-proposal.qmd` | Metadata, adapters, validation, registry, and review milestones |
| `proposal/04-timeline.qmd` | Preliminary work, schedule, budget, and risks |
| `proposal/05-success.qmd` | Completion criteria, adoption measures, and future work |
| `references.bib` | Citations |
| `_extensions/` | Hikmah PDF format from the official ISC template |

The proposal uses the [official ISC template](https://github.com/RConsortium/isc-proposal).
