# blocklength 0.2.2

## Minor Changes

* The `plot.nppi()` function now returns an additional plot for JAB Pseudo Value Stability. 


## Bug Fixes

* In `nppi()` there was an inconsistency in dimensionality between the `jab_point_values` and the `jab_pseudo_values` due to how NA values were handled. This is fixed such that both vectors will always have the same length.


# blocklength 0.2.1

## Minor Changes

* The `nppi()` function now returns an additional item in the `nppi` object: `jab_pseudo_values` which include the *ith MBJ pseudo-value* used in the JAB variance estimator.


## Bug Fixes

* In `nppi()` there was an incorrect computation of the JAB variance estimator, which did use the *ith MBJ pseudo-value* in place of the the *ith MBJ point value*. This is now fixed.



# blocklength 0.2.0

## New features

* A new function `nppi()` has been added to the package. This function estimates the optimal block-length using the non-parametric plug-in (NPPI) method of Lahiri, Furukawa, Lee, (2007).

* A new S3 plot method `plot.nppi()` has been added to the package. This function outputs a diagnostic plot for JAB point values calculated from the above `nppi()` function.


# blocklength 0.1.5

* Minor adjustments to documentation per CRAN requests.


# blocklength 0.1.4


## Bug Fixes

* In `pwsd()`, `m_hat` was indexing the first insignificant lag of the correlation structure rather than the first *significant* lag prior to the consecutive run of insignificant lags.

* `pwsd()` and `plot.pwsd()` now output significance bands that match `rho_k_critical` exactly. Prior to this, the significance bands on the correlogram output were generated using the `plot.acf(ci = )` argument which led to misleading graphical representations of the implied hypothesis test's critical value in the PWSD method.

* In `hhj()`, `sub_block_length` has been changed to `sub_sample` to avoid confusion with the other tuning parameter, `pilot_block_length`


## Minor Changes

* A new vignette has been included on tuning and diagnosing problematic output from the selection functions!

* `pwsd()` now includes a new argument to override the implied hypothesis test by setting `m_hat` directly.

* In `pwsd()`, `rho.k.critical` has been changed to snake case `rho_k_critical` in the `$parameters` matrix from output of class 'pwsd' objects from `pwsd().`

* In `hhj()`, if `subsample = ` is set directly it is now rounded to the nearest whole number.

* `plot.pwsd()` now includes "darkmagenta" significance lines to match `pwsd().`

* `plot.pwsd()` now explicitly includes an option to customize title with `main = .`

* `hhj()` now includes a warning message if the supplied iteration limit `n_iter` is reached but still outputs an object of class 'hhj.'


# blocklength 0.1.3

* This is the first submission accepted to CRAN
* Minor changes to documentation and testing of examples


# blocklength 0.1.0

* This is the first submission of blocklength package.
