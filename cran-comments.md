## Resubmission
This is a patch release to address specific user-reported bugs and numerical limitations in the underlying C++ algorithm integration boundaries.

## Test environments
* Local Windows 11 install, R 4.5.0
* ubuntu-latest (on GitHub Actions/R-hub), R-release, R-devel
* macOS-latest (on GitHub Actions/R-hub), R-release
* windows-latest (on GitHub Actions/R-hub), R-release

## R CMD check results

0 errors | 0 warnings | 1 notes

* NOTE: 
  checking compiled code ... NOTE
  unable to translate '.../MomTrunc.dll' to a wide string.
  (This is a local Windows encoding issue caused by the presence of a Spanish character 'é' in the local build path. It is entirely unrelated to the package code).

## Changes
* Fixed a mathematical stability warning inside `pmvEST` where the degrees of freedom parameter was passed incorrectly.
* Exposed `maxpts` and `abseps` global integration precision parameters for `momentsTMD` algorithms through Rcpp wrappers, allowing end-users to compute immensely high dimensional truncation requests by decreasing the algorithmic margin of error at will.

## Downstream dependencies
I have run `R CMD check` on downstream dependencies of MomTrunc. All checks passed successfully.
