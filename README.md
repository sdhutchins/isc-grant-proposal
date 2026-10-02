# tutorialverse ISC proposal

A proposal to the R Consortium Infrastructure Steering Committee for shared metadata, validation, discovery, and review infrastructure across R tutorial engines.

- [Proposal source](isc-proposal.qmd) and [sections](proposal/)
- [tutorialverse prototype](https://github.com/tutorial-verse/tutorialverse)
- [Official ISC template](https://github.com/RConsortium/isc-proposal)

## Render

Requires [Quarto](https://quarto.org/) and LaTeX. Install TinyTeX if needed with `quarto install tinytex`.

```sh
quarto render isc-proposal.qmd --to hikmah-pdf
quarto render isc-proposal.qmd --to html
```

Generated PDF and HTML files are not tracked in Git.
