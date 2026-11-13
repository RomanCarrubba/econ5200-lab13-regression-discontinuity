# econ5200-lab13-regression-discontinuity

z# Regression Discontinuity: Bandwidths, Manipulation and Close Elections

## Objective

I compared how global and local regression discontinuity estimators perform on simulated and real data, and tested whether their key assumptions hold.

## Methodology

- I simulated a grant program with a true effect of 8 percentage points at a cutoff.
- I estimated the effect two ways: a global quadratic fit, and a local linear fit at a data-driven bandwidth.
- I repeated the simulation 300 times and compared the root mean squared error across bandwidths.
- I ran a density test for manipulation of the running variable on data where I had moved units across the cutoff.
- I ran a covariate continuity test at the cutoff.
- I applied the design to US House elections, following Lee, Moretti and Butler (2004), to estimate how much more liberally a district is represented when a Democrat barely wins. I used ADA scores as the outcome.
- I wrote my own local linear RD estimator with a triangular kernel and checked it against the rdrobust package.

## Key Findings

- The global quadratic estimated an effect of 0.0357, and the local linear fit at a bandwidth of 3 estimated 0.0789. The true effect was 8 percentage points.
- Across the 300 repetitions, the root mean squared error was smallest at a bandwidth of 20.
- The density test gave p = 0.965 on the data where units moved across the cutoff.
- The covariate continuity test showed 5.243.
- In the House elections, a narrow Democratic win was associated with a 46.491 ADA point increase in how liberally the district is represented.
- My own estimator matched rdrobust's point estimate, confirming that my implementation of the local linear RD with a triangular kernel was correct
