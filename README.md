# Stacking Spectra of QSOs and Galaxies

This repository preserves the original notebook from my Summer 2024 project with **Prof. Shadab Alam at TIFR Mumbai**. The main exercise was to retrieve spectra through SPARCL, place them on a common rest-frame wavelength range, and compare simple and inverse-variance-weighted stacks. The report is dated 4 September 2024.

The broader group project studied QSOs as tracers of the Universe and discussed their relation to galaxies, dark-matter haloes, and large-scale structure. The TIFR project page also lists possible questions about QSO redshift errors, groups, and merger signatures. Those broad themes should not be confused with results from this repository: the notebook here is a spectral-stacking exercise, not a clustering or halo-occupation analysis.

## What is in this repository

- `Stacked Spectrum Code.ipynb` — the original 2024 notebook, retained unchanged during this review. It includes one saved SDSS DR16 QSO example (100 objects; redshift 0.6–1.1; RA and Dec 0–10 degrees) and saved plots. The notebook prints the sample's SPARCL `specid` values.
- [Original Summer 2024 project report](TIFR Summer Project 2024 Report.pdf) — the report submitted for the 2024 project.
- `docs/methods-and-limitations.md` — the method as implemented, its scientific assumptions, and issues identified in a later review.
- `docs/reproducibility.md` — the sample selection and what is needed to rerun it.
- `docs/references.md` — project, data, software, and scientific reference links with their roles.
- `CITATION.cff` — citation metadata.
- `LICENSE` — MIT License.

The report discusses SDSS DR16, BOSS DR16, and DESI EDR, but the current notebook does not contain runnable examples for all three releases. It does not fit emission lines, estimate AGN physical properties, or measure large-scale structure.

## Historical work and later improvements

The notebook and report record my completed spectral-stacking project from the Summer Project of 2024 under Prof. Shadab Alam. I’m now revisiting the notebook to clarify the methods and correct parts of the implementation and explanation as needed.

## Related black-hole kick work

During the Summer 2024 project, I also explored black-hole merger kick velocities. I learned about kick velocities and worked with simulations, but did not complete a separate, reproducible numerical analysis.

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
