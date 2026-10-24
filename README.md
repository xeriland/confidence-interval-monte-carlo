# When 95% Isn't 95%: A Monte Carlo Investigation of Confidence Interval Reliability

## Overview

A nominal 95% confidence interval is designed to contain the true population parameter in approximately 95% of repeated samples. However, actual coverage depends on the statistical procedure, sample size, and characteristics of the population distribution.

This project uses Monte Carlo simulation to investigate the reliability of conventional Student's t confidence intervals and percentile bootstrap confidence intervals for estimating a population mean.

The analysis focuses on how sample size and population skewness influence empirical coverage probability and average interval width.

## Research Question

How do sample size and population distributional shape jointly affect the empirical coverage probability and average width of nominal 95% confidence intervals when conventional Student's t intervals are compared with percentile bootstrap intervals?

## Methodology

The simulation examines:

- **Sample sizes:** 10, 30, 100, and 500
- **Population distributions:** Normal, moderately skewed gamma, and strongly skewed exponential
- **Confidence interval methods:** Student's t and percentile bootstrap
- **Monte Carlo replications:** 1,000 per experimental condition
- **Bootstrap resamples:** 1,000 per Monte Carlo replication
- **Population parameters:** Mean = 100; standard deviation = 15

All three populations share the same mean and standard deviation, allowing the effects of distributional shape to be examined separately.

The simulation evaluates 12 experimental conditions, comparing the empirical coverage and average width of both interval methods.

## Key Findings

1. Conventional Student's t intervals generally maintained coverage close to the nominal 95% level under normality.

2. Percentile bootstrap intervals exhibited substantial undercoverage at small sample sizes, particularly when n = 10.

3. Strong population skewness reduced confidence interval coverage, especially for smaller samples.

4. Increasing sample size generally improved coverage reliability and reduced interval width.

5. Percentile bootstrap intervals frequently produced narrower intervals but did not consistently achieve better coverage than conventional t intervals.

These results demonstrate that bootstrap confidence intervals are not automatically more reliable than traditional parametric intervals.

## Visualizations

The repository includes three figures:

- `coverage_by_sample_size.png` — Student's t interval coverage across sample sizes and distributions.
- `bootstrap_coverage.png` — Percentile bootstrap interval coverage across sample sizes and distributions.
- `coverage_difference.png` — Difference in empirical coverage between bootstrap and t intervals.

## Reproducibility

The complete simulation is implemented in Python using NumPy, pandas, SciPy, and Matplotlib.

Install the required dependencies:

```bash
pip install -r requirements.txt
```

Run the simulation:

```bash
python statistical_simulation.py
```

The program generates a CSV file containing the simulation results and three PNG figures.

Fixed random seeds are used to support reproducibility.

## Limitations

The investigation considers three population distributions, four sample sizes, and two confidence interval procedures. Results may not generalize to other distributional characteristics or statistical parameters.

Coverage estimates are also subject to Monte Carlo sampling uncertainty. More advanced bootstrap methods, including BCa and studentized intervals, were not examined.

## Conclusion

The reliability of a nominal 95% confidence interval depends on more than its stated confidence level.

This simulation illustrates the importance of considering sample size, population distribution, and interval construction method when conducting statistical inference.

The findings are particularly relevant to applied research in psychology, education, and business analytics.
