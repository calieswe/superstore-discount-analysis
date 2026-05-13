# Do Discounts Significantly Increase Revenue? A Statistical Study

## Overview

This project uses descriptive statistics and hypothesis testing to answer a real retail business question: do discounts significantly increase sales revenue, or do they erode margin without a meaningful uplift? Although retailers routinely apply discounts to drive purchases, the actual statistical effect on revenue is rarely tested. This analysis tests the difference in mean revenue between discounted and non-discounted transactions using a two-sample unpaired t-test.

Completed as part of the Statistics I module on the Higher Diploma in Science in Data Analytics at the National College of Ireland.

## Dataset

The Superstore dataset from Kaggle (https://www.kaggle.com/datasets/vivek468/superstore-dataset-final), containing 9,994 transactions with variables including Sales (revenue per transaction), Discount, Quantity, Category, and Region. After data cleaning, two groups were created for analysis: 5,196 discounted transactions and 4,798 non-discounted transactions.

## Methods

1. **Data preparation** — Missing values were removed and incomplete rows dropped.
2. **Descriptive analysis** — Mean, median, standard deviation, skewness, and kurtosis were computed for the Sales variable. Raw Sales was extremely right-skewed (skewness = 10.25, kurtosis = 183.14), violating t-test assumptions.
3. **Log transformation** — A log transformation was applied to stabilise variance and improve normality. Skewness reduced from 10.25 to 0.185.
4. **Normality check** — A Q-Q plot compared observed log-Sales values against theoretical normal quantiles, confirming approximate normality.
5. **F-test for variance equality** — Tested whether the two groups had equal variances (F = 1.64, F-critical = 1.05, p < 0.001). The null was rejected, so the unequal-variances version of the t-test (Welch's t-test) was selected.
6. **Welch's two-sample t-test** — Tested whether discounted transactions have a higher mean log-Sales than non-discounted transactions.

## Key Findings

- The mean log-Sales for discounted transactions (5.41) was substantially higher than for non-discounted transactions (2.70).
- The t-statistic of **147.10** (df = 9,727) was far above the critical value of 1.64, and the p-value was effectively zero.
- The null hypothesis was rejected with very high confidence: **discounts significantly increase revenue** at the transaction level.
- A noted limitation is that the analysis grouped all discounted transactions together, ignoring different discount levels. A follow-up analysis comparing discount tiers (e.g. 10%, 20%, 30%) would be a logical next step.

## Tools

- **Microsoft Excel** — descriptive statistics, log transformation, Q-Q plot, F-test, Welch's t-test
- **Excel charting** — histograms, boxplots, Q-Q plot

## Files

- `SWE SWE AUNG_Statistics I (HDSDADINTJAN26I)_CA.pdf` — Full project report with methodology, charts, and results.
