# Building and checking mirrorslope

The package is complete. These steps finalise the generated documentation and
verify it, and must run on a machine with CRAN access (this build environment
did not have it). Run them from inside the package directory (the folder
containing `DESCRIPTION`).

## 1. Install the tooling (once)

```r
install.packages(c("devtools", "roxygen2", "testthat",
                   "ggplot2", "dplyr", "rlang", "knitr",
                   "rmarkdown", "patchwork"))
```

## 2. Generate help files and NAMESPACE from the roxygen comments

```r
devtools::document()
```

This creates `man/*.Rd` and regenerates `NAMESPACE` from the `@` tags already
present in the source. After this, `?mirror_slope_plot` will work.

## 3. Run the test suite

```r
devtools::test()
```

Expect all tests to pass. The utility and pipeline tests were verified during
development; the plot tests confirm ggplot objects are returned.

## 4. Full package check

```r
devtools::check()
```

Target: 0 errors, 0 warnings, 0 notes. If a note appears about undefined global
variables, it will name the offending symbols; they are handled via the
`.data[[]]` pronoun and explicit `::` calls, so a clean `document()` run should
resolve it.

## 5. Build the vignettes (optional preview)

```r
devtools::build_vignettes()
```

## 6. Install locally

```r
devtools::install()
```

## Notes

* Minimum R version is 4.0.0 (declared in DESCRIPTION); the pipe used in
  examples is the base `|>` from R 4.1+, so run examples on R >= 4.1.
* The `mirror_data` specification shared with the SAS macro is in
  `inst/mirror_data_specification.md`.
