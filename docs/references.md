# Project and reference links

This map preserves the links supplied for the project and notes their apparent roles. “Not verified” means the link could not be read directly during the October 2026 review; its role is not inferred beyond its visible URL or surrounding project context.

## Project overview and collaboration or working material

- [TIFR Summer Project overview](https://www.tifr.res.in/~shadab.alam/SummerProject/) — overview of the Summer 2024 group project, whose broad theme was QSOs as tracers of the Universe. It lists possible questions about QSO/galaxy and halo connections, merger signatures, redshift errors, and galaxy groups. It is project context, not evidence that every question was an individual result.
- [LSS-HandsON on GitLab](https://gitlab.com/shadaba/lss-handson) — group Jupyter notebooks for large-scale-structure analysis with a correlation-function code. It is a learning/collaboration resource, not the spectral-stacking repository.
- [OneDrive presentation](https://1drv.ms/p/c/fb8032fbeb3352df/ES75ZX1Jd0xHrwEnbmXzBbwB-MM969MToR_WAbNUSb7ZsQ?e=6h1plz) — presentation link supplied by the author. Not accessible during review; contents and precise role remain unverified.

## Spectral analysis, catalogues, data services, and software

- [`redrock`](https://github.com/desihub/redrock) — DESI redshift-fitting software; not imported or called by the current notebook.
- [Astro Data Lab overview](https://datalab.noirlab.edu/about) — NOIRLab data-platform context.
- [SPARCL usage notebook](https://github.com/astro-datalab/notebooks-latest/blob/master/04_HowTos/SPARCL/How_to_use_SPARCL.ipynb) — external example for using SPARCL.
- [SPARCL service](https://astrosparcl.datalab.noirlab.edu/) — remote spectra service used by the notebook; direct page access was blocked during review.
- [SPARCL User Manual](https://astrosparcl.datalab.noirlab.edu/static/SPARCLUserManual.pdf) — service manual; direct access was blocked during review.
- [SPARCL client documentation](https://sparclclient.readthedocs.io/en/latest/sparcl.html) — documentation for the Python client and service query/retrieval methods.
- [SDSS eBOSS overview](https://www.sdss4.org/surveys/eboss/) — survey context; not a runnable BOSS sample in the current notebook.
- [SDSS DR16 introduction](https://skyserver.sdss.org/dr16/en/help/docs/intro.aspx) — DR16 documentation; page could not be retrieved during review.
- [SDSS DR18 plate tool](https://skyserver.sdss.org/dr18/MoreTools/plate) — plate lookup tool from DR18, a different release than the DR16 example.
- [eROSITA science portal](https://erosita.mpe.mpg.de/) — X-ray survey and AGN context; not used in the current stacking notebook.

## Scientific papers and written references

- [Impact of tidal environment on galaxy clustering in GAMA (arXiv:2305.01266)](https://arxiv.org/abs/2305.01266) — galaxy-environment and clustering context; not a spectral-stacking method paper.
- [UPC repository PDF](https://upcommons.upc.edu/server/api/core/bitstreams/c8050aa7-586a-4fae-8de0-8c7e68d49f29/content) — access returned 403 during review. Title and relevance could not be verified.
- [Black-hole kicks from numerical-relativity surrogate models (arXiv:1802.04276)](https://arxiv.org/pdf/1802.04276) — scientific background for the separate kick-velocity follow-up.
- [A Beginner’s Guide to Working with Astronomical Data (HTML)](https://ar5iv.labs.arxiv.org/html/1905.13189) and [the same work as an arXiv PDF](https://arxiv.org/pdf/1905.13189) — two formats of the same general astronomy data guide.
- [Broad emission lines in optical spectra of hot dust-obscured galaxies can contribute significantly to JWST/NIRCam photometry](https://arxiv.org/abs/2301.00017) — the paper identified from the report's McKinney et al. (2023) reference. It uses a stack of 21 Keck/NIRES spectra and quantitative line measurements; the current notebook does not reproduce its sample or analysis.

## Kick-velocity software

- [`surrkick` on GitHub](https://github.com/dgerosa/surrkick?tab=readme-ov-file) — related software; direct page reading was unavailable during review.
- [`surrkick` on PyPI](https://pypi.org/project/surrkick/#files) — package distribution page for the same tool.

## Clipping and numerical-method references

- [Astropy `sigma_clip`](https://docs.astropy.org/en/stable/api/astropy.stats.sigma_clip.html) — configurable sigma clipping; the documented default centers on the median and handles invalid values.
- [SciPy `sigmaclip`](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.sigmaclip.html#scipy.stats.sigmaclip) — iterative clipping centered on the mean by default; behavior differs from Astropy's default.
- [GNU Astronomy Utilities: Sigma-clipping](https://www.gnu.org/software/gnuastro/manual/html_node/Sigma-clipping.html) — method reference cited in the report; direct page reading was unavailable during review.

## Acknowledgements and attribution

The report acknowledges SPARCL, Astro Data Lab, NOIRLab/CSDC, SDSS, and DESI. Retain their required acknowledgements when redistributing outputs or adapting code, and check the relevant survey/service terms for each dataset used.
