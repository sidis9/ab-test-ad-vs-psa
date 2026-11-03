# Ad vs PSA A/B Test Analysis (Public Dataset)

**This is a portfolio project using a public Kaggle dataset, not data from an employer or a business I run.**
Dataset: [Marketing A/B Testing on Kaggle](https://www.kaggle.com/datasets/faviovaz/marketing-ab-testing). The data file is not included here. Download it from Kaggle and place `marketing_AB.csv` next to the notebook.

## Question
Did people who saw the ad buy at a higher rate than people who saw the PSA (public service announcement), and should a marketer keep spending on ads?

## Groups and sizes
588,101 people, each in exactly one group. No empty cells, no repeated rows, no repeated users.

| Group | People | Buyers |
|---|---|---|
| Ad | 564,577 | 14,423 |
| PSA | 23,524 | 420 |

The PSA group is about 24 times smaller, so its rate is less steady.

## Metric
Conversion rate: the share of people who bought.
Ad 2.555%. PSA 1.785%.

## Test
Two proportion z test (Python, statsmodels), two sided, 95% confidence.
Z statistic 7.37. P value 1.705e-13. Gap (ad minus PSA) 0.769 percentage points, 95% confidence interval 0.595 to 0.943.

## Result in plain words
The ad group bought at a higher rate, and luck is an unlikely explanation. The real gap is likely between 0.6 and 0.9 percentage points. The ad group was also higher on all 7 days of the week, but the daily numbers are small and exploratory.

## Decision for a marketer
Keep running the ads if the extra buyers are worth more than the ads cost. A gap of 0.769 points is about 769 extra buyers per 100,000 people shown the ad (likely 595 to 943). The data has no ad cost or sale value, so profit cannot be judged from it.

## Limits
- The file does not show how people were assigned to groups, so this analysis does not prove the ads caused the gap.
- The PSA group is much smaller than the ad group.
- Only bought or not bought is recorded. No revenue, cost, or dates.
- The day of week breakdown is exploratory, built on small daily PSA groups.
- Public dataset. The product and market are unknown.

## Files
`ab_test.ipynb`: full analysis with code and output.
