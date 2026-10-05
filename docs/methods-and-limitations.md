# Methods, assumptions, and limitations

## Historical context

The report describes a Summer 2024 group project at TIFR Mumbai supervised by Prof. Shadab Alam. Its broad scientific context was QSOs as tracers of large-scale structure and their connection to galaxies and dark-matter haloes. This repository preserves the individual spectral-stacking notebook and report; it does not contain a clustering measurement or a halo model.

The report also mentions work with black-hole merger simulations. It provides no kick-velocity derivation, parameter sampling record, output table, or numerical result. That work is therefore described separately as an unfinished personal follow-up, not as a completed result of the stacking project.

## Original notebook workflow

1. Query SPARCL for QSO records and retrieve wavelength, flux, inverse variance, and redshift.
2. Convert observed wavelength to a rest-frame wavelength using
   \[
   \lambda_{\rm rest}=\frac{\lambda_{\rm obs}}{1+z}.
   \]
   This is the conventional wavelength relation for redshift `z`. The notebook leaves the numerical flux-density values unchanged; see the open convention question below.
3. Apply the CCM89 extinction curve with `R_V = 3.1`. The sample code sets `E(B-V) = 0.1` for every spectrum, rather than documenting a per-object source for those values.
4. Restrict the example to 2440–6000 Å in the wavelength variable, assign samples to logarithmic wavelength bins, and apply an iterative clipping routine described as a median-centered `n = 3` clip with tolerance `0.7`.
5. Plot an arithmetic mean and a purported inverse-variance-weighted mean, with a Gaussian-smoothed curve for display.

The conventional inverse-variance mean for fluxes `f_i` and inverse variances `w_i = 1/σ_i²` is
\[
\bar f = \frac{\sum_i w_i f_i}{\sum_i w_i}.
\]
This is the equation stated in the report. It is not what the current `weigh_mean` function computes because the stored columns are indexed in the wrong order.

## Findings from the retrospective review (October 2026)

These are findings, not claims that fixes have already been applied:

- **Weighted mean:** Each point is stored as `[log wavelength, inverse variance, flux]`. The current function takes column 1 as the value and column 2 as its weight, reversing the intended flux and weight. The separately calculated per-bin variance list is not used in that function.
- **Clipping:** The routine first computes a standard deviation from flux values. After clipping, however, it calls `np.std` on the complete rows, mixing log wavelength, inverse variance, and flux. The resulting quantity is not the clipped flux spread. The tolerance is also unusually permissive and should be evaluated, not silently changed.
- **Dust correction and uncertainty:** The code multiplies flux by the extinction correction but leaves inverse variance unchanged. For a multiplicative flux factor `C`, inverse variance must be transformed consistently if it is to remain the weight for the corrected flux. The physical source and appropriateness of the fixed `E(B-V)=0.1` need confirmation.
- **Masks and invalid values:** The notebook retrieves inverse variance but does not use it to reject invalid, non-finite, or non-positive-weight pixels before clipping and stacking. Empty bins are plotted as zero, which can be mistaken for measured flux.
- **Wavelength bins:** The estimated log step uses `(last - first) / N` rather than dividing by the number of intervals. Bin assignment includes both ends of each interval, so a point exactly on a shared edge can be counted twice. Shapes, non-finite values, missing records, and empty bins need explicit handling.
- **Frame and units:** Wavelength is moved to the rest frame, but `f_lambda` is not rescaled. If the intended plotted quantity is a rest-frame flux density per Å, the density convention must be stated and applied consistently to the flux and uncertainty. If the intent is only to relabel the wavelength axis while retaining observed flux density, the plot and documentation must say so. This is a scientific choice requiring review.
- **Interpretation:** The notebook does not perform continuum fitting, emission-line fitting, AGN parameter estimation, or environment/clustering analysis. Recognizable features in a stacked plot are not by themselves quantitative line measurements or evidence that one estimator is generally more reliable.
- **Report consistency:** The report discusses three releases and gives SDSS and BOSS examples; the current notebook contains one SDSS DR16 QSO example. The report captions call all four plots weighted-mean plots, although the first two axes say “Mean” and the latter two say “Weighed Mean.”

## Original choices versus later changes

The steps above describe the 2024 notebook, including choices that need review. Any later implementation should:

1. preserve this notebook unchanged as the historical version;
2. be clearly named and dated as a corrected or extended version;
3. list the exact changed assumptions and code behavior;
4. provide tests or example checks for array shape, invalid values, empty bins, bin-edge assignment, clipping, and weighted means; and
5. report what was actually run, with its input sample and environment.

No later scientific results should be added to the project description until their data and calculations are available for inspection.
