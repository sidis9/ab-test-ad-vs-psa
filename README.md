# Ad vs PSA A/B Test Analysis (Public Dataset)

**Result:** In a public Kaggle dataset of 588,101 people, the ad group bought at 2.555% versus 1.785% for the PSA group, a gap of 0.77 percentage points (95% interval 0.60 to 0.94), so the ad group did better and luck is an unlikely explanation.

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
Keep running the ads if the extra buyers are worth more than the ads cost. The ad group had about 769 more buyers per 100,000 people than the PSA group (likely 595 to 943). If the ads caused that gap, that is the extra buyers they
