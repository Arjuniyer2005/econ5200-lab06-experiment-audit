# econ5200-lab06-experiment-audit
# Experiment Design Audit — Power, Selection & Weighting

## Objective

I audited an underpowered A/B test and a biased observational comparison to show how experimental design and non-random selection can distort results.

## Methodology

- Calculated the power of an A/B test with 1,000 treatment users and 49,000 control users.
- Estimated the sample size needed to detect a 0.8 percentage-point lift with 80% power.
- Wrote a `power_check` function and compared it with the statsmodels result.
- Diagnosed selection bias in a voluntary wellness program where baseline health affected both participation and healthcare costs.
- Used inverse probability weighting to adjust for differences in treatment probability.

## Key Findings

The original A/B test had only **19.8% power** to detect a 0.8 percentage-point lift. Reaching 80% power required about **12,514 users per group**. With the same 50,000 users split evenly, the experiment would have had about **97.7% power**.

In the wellness-program analysis, the naive comparison estimated an effect of about **-$1,396**, compared with the true effect of **-$500**. After applying inverse probability weighting, the estimate improved to about **-$522**.

The main lesson from the lab is that having a large dataset does not guarantee a reliable result. How observations are assigned or selected can matter as much as the total sample size.
