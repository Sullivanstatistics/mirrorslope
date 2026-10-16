## R CMD check results

0 errors | 0 warnings | 1 note

* This is a new release (the only NOTE is "New submission").
* Checked locally with `--as-cran` on Windows 11, R 4.5.3 (ucrt); spelling checked with the spelling package (en-GB, inst/WORDLIST).
* win-builder R-release (R 4.6.1, 16 Oct 2026): 1 NOTE (New submission; the spell check flags the names Kati and
  Maharry in the Description field, which are a person's name). PDF and HTML manuals built OK.
* [Fill in: win-builder R-devel result; R-hub GitHub Actions workflow (linux, windows, macos).]

## Notes for the reviewer

* The package draws figures only; it fits no models. All numbers on the figure are values the user supplies.
* The display was designed by Kati Maharry; the method is described in Maharry and Sullivan (2026, manuscript in
  preparation) and was first used in the supplementary appendix of McDonald et al., Lancet 2026
  (doi:10.1016/S0140-6736(26)01385-1). The Description field cites the published use; the manuscript DOI will be
  added when available.
