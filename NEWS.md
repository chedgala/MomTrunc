# MomTrunc 6.1.1

## Bug Fixes

* Corrected the calculation for the multivariate extended student-t distribution CDF (`pmvEST`) probabilities to properly parameterize the degrees of freedom `nu` rather than incorrectly passing `nu+1` to the underlying multivariate Student-t call, fixing reported issues where evaluated probability values were significantly lower than 1 across infinite bounding geometries.
* Modified the mathematical stability tolerance for highly demanding recurrence relation queries with enormous total polynomial order values (`momentsTMD`). It intrinsically multiplies quasi-Monte Carlo variance iteratively from base calculations (Genz algorithm). To provide options for power-users running these corner cases, explicit precision parameters (`maxpts` and `abseps`) have been surfaced up to the package's primary R API natively bridging directly into the core C++ loops, allowing absolute precision management without sacrificing basic routine speed.
