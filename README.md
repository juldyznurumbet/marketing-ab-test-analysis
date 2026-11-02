# Marketing-AB-Test-Analysis
A/B test on 588K users: does advertising drive sales? Ad vs PSA control, +43% conversion lift. Z-test, chi-square, Mann-Whitney, bootstrap and frequency analysis in Python.

## Does Advertising Drive Sales? Marketing A/B Test Analysis

Analysis of an A/B test on 588,101 users to measure whether an ad campaign increases purchases compared with a control group shown a public service announcement (PSA).

## Key results

- **The ad works:** conversion is **2.55%** (ad) vs **1.79%** (PSA), a **+43% relative lift** (+0.77 pp, 95% CI: 0.59–0.94 pp, p < 0.001).
- **~4,300 incremental purchases**: about 30% of the ad group's purchases were caused by the ad; the rest would have happened anyway.
- **Optimal frequency is 50–200 impressions per user**: below 20 and above 200 impressions, the ad shows almost no effect vs control.

## Business question

Do users who see a product ad convert more than users who don't? And if so, how should the campaign be optimised (frequency, timing)?

## Dataset

[Marketing A/B Testing](https://www.kaggle.com/datasets/faviovaz/marketing-ab-testing) (Kaggle)

| Column | Description |
|---|---|
| `test group` | `ad` (96% of users) or `psa` (control, 4%) |
| `converted` | whether the user made a purchase |
| `total ads` | number of ads the user saw |
| `most ads day` / `most ads hour` | when the user saw the most ads |

## Approach

1. **Data checks**: group sizes, ad exposure, day distribution
2. **Shapiro–Wilk**: normality check on ad exposure
3. **Mann–Whitney U**: confirms both groups saw a similar number of ads (median 13 vs 12)
4. **Chi-square**: day-of-week distribution between groups
5. **Z-test for two proportions**: main conversion comparison
6. **Bootstrap (1,000 resamples)**: assumption-free confirmation of the confidence interval
7. **Ad hoc analysis**: lift by day, hour and ad frequency

## Tools

Python · pandas · NumPy · SciPy · statsmodels · Matplotlib · seaborn

## How to run

1. Download `Marketing_AB.csv` from the Kaggle link above
2. Place it in the same folder as the notebook
3. Run the notebook top to bottom
