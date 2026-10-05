# Stacking Spectra of QSOs and Galaxies

This repository preserves the original notebook from my Summer 2024 project with **Prof. Shadab Alam at TIFR Mumbai**. The main exercise was to retrieve spectra through SPARCL, place them on a common rest-frame wavelength range, and compare simple and inverse-variance-weighted stacks. The report is dated 4 September 2024.

The broader group project studied QSOs as tracers of the Universe and discussed their relation to galaxies, dark-matter haloes, and large-scale structure. The TIFR project page also lists possible questions about QSO redshift errors, groups, and merger signatures. Those broad themes should not be confused with results from this repository: the notebook here is a spectral-stacking exercise, not a clustering or halo-occupation analysis.

## What is in this repository

- `Stacked Spectrum Code.ipynb` — the original 2024 notebook, retained unchanged during this review. It includes one saved SDSS DR16 QSO example (100 objects; redshift 0.6–1.1; RA and Dec 0–10 degrees) and saved plots. The notebook prints the sample's SPARCL `specid` values.
- `docs/methods-and-limitations.md` — the method as implemented, its scientific assumptions, and issues identified in a later review.
- `docs/reproducibility.md` — the sample selection and what is needed to rerun it.
- `docs/references.md` — project, data, software, and scientific reference links with their roles.
- `CITATION.cff` — citation metadata.
- `LICENSE` — GNU General Public License, version 3.

The report discusses SDSS DR16, BOSS DR16, and DESI EDR, but the current notebook does not contain runnable examples for all three releases. It does not fit emission lines, estimate AGN physical properties, or measure large-scale structure.

## Historical work and later improvements

The notebook and report are the record of the original student work. A retrospective review in October 2026 identified implementation and documentation problems, including incorrect column use in the weighted mean and a clipping calculation that takes a spread over whole rows instead of fluxes. The report's figure captions also label all four plots as weighted means, although the plotted axes distinguish simple and weighted means.

These issues are disclosed here so the development history remains visible. **The original notebook has not been silently replaced, and this documentation draft does not claim the code issues are already fixed.** Later corrections should be added as a clearly named, dated version or file, with the original notebook preserved and the decisions and checks recorded. Scientific choices that remain ambiguous—especially dust correction and rest-frame flux-density convention—must be explained before they are changed.

## Related black-hole kick work

The report says I worked with black-hole merger simulations and learned about kick velocities, but it does not document a method, numerical results, or a completed deliverable for that work. I am treating the kick-velocity analysis as a separate, unfinished personal follow-up, not as a completed result of the spectral-stacking project. The repository should not claim kick values or conclusions unless a later, reproducible analysis supports them.

## Running the original notebook

The notebook was recorded with Python 3.10.13 and imports the SPARCL client, NumPy, Astropy, Specutils, Matplotlib, pandas, and the `extinction` package, among other modules. Exact package versions and a complete environment file were not recorded. See [reproducibility notes](docs/reproducibility.md) before attempting a rerun; the saved plots are not proof of a fresh execution.

## Original acknowledgement and references

The following acknowledgement and two references are retained from the original README:

This research uses services or data provided by the SPectra Analysis and Retrievable Catalog Lab (SPARCL) 
and the Astro Data Lab, which are both part of the Community Science and Data Center (CSDC) Program of NSF NOIRLab.
NOIRLab is operated by the Association of Universities for Research in Astronomy (AURA), Inc. under a cooperative agreement with the U.S. National Science Foundation.

Data Lab concept paper: Fitzpatrick et al., "The NOAO Data Laboratory: a conceptual overview", SPIE, 9149, 2014, https://doi.org/10.1117/12.2057445

Astro Data Lab overview: Nikutta et al., "Data Lab - A Community Science Platform", Astronomy and Computing, 33, 2020, https://doi.org/10.1016/j.ascom.2020.100411

See the [reference map](docs/references.md) for the complete source list supplied for this project.
