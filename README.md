# Product Analytics & Data Science Statistics: Test Assignment

Completed test assignment for a **Product Analyst / Data Analyst** position. It covers **product metrics**, **A/B testing**, **hypothesis testing** and **applied statistics**, solved in Python (Jupyter Notebook), with answers to all questions in a Word document.

## Topics Covered
**Product Analytics**
- MAU (Monthly Active Users)
- DAU (Daily Active Users) and daily activity dynamics
- Retention (Day 1 retention, cohort analysis, retention curves)
- User conversion
- NPS (Net Promoter Score)
- ARPU (Average Revenue Per User)
- Revenue per user, user-level aggregation

**A/B Testing & Hypothesis Testing**
- A/B test analysis and interpretation of results
- Welch's t-test (comparison of means)
- Mann–Whitney U test (non-parametric test)
- Z-test for two proportions (conversion comparison)
- Chi-square test for SRM (Sample Ratio Mismatch)
- p-value interpretation, statistical significance
- Recommendations: roll out / roll back / extend the test

**Data Science Statistics**
- Descriptive statistics: mean, median, quartiles, variance
- Distributions: bimodal distribution, density plots, outliers
- Choosing the right test: t-test, chi-square, ANOVA, Pearson correlation
- Data visualization: box plot, histogram, scatter plot, line chart

## Data
| File | Description |
|---|---|
| `Данные для тестового задания - Данные об аудитории.csv` | App users in November 2023 (16,814 rows): `date`, `user_id`, `view_adverts` |
| `Данные для тестового задания - Данные АБ тестов.csv` | Results of 3 A/B tests: `experiment_num`, `experiment_group`, `user_id`, `revenue` |
| `Данные для тестового задания - Листеры.csv` | Listers data: `user_id`, `date`, `cnt_adverts`, `age`, `cnt_contacts`, `revenue` |

## Key Results
| # | Task | Result |
|---|---|---|
| 1 | MAU | **7,639** |
| 2 | Average DAU | **560** |
| 3 | Day 1 retention (users who came on 1 Nov) | **26.6%** (166 of 623) |
| 4 | Retention curves | Blue product plateaus at ~38–40% (product-market fit), red product drops to 0% by day 5 |
| 5 | User conversion to advert view | **46.3%** |
| 6 | Average adverts viewed per user | **2.9** |
| 7 | NPS | **35%** |
| 8 | A/B tests (ARPU) | see below |
| 9 | Average revenue per lister | **≈156.4** (aggregated per user, not per row) |
| 10 | Median lister age | **28** |
| 18 | Conversion A/B test | z-test p ≈ 0.035, but SRM detected (p ≈ 0.001) |

### A/B Tests (Task 8)
| Experiment | ARPU control → test | t-test p-value | Mann–Whitney p-value | Decision |
|---|---|---|---|---|
| 1 | 723 → 666 | 0.689 | 0.796 | No effect, no reason to roll out |
| 2 | 705 → 333 | 0.001 | 0.009 | Significant **drop**, roll back |
| 3 | 663 → 999 | 0.060 | 0.001 | Promising but not proven by mean (outliers), extend the test |

Note: all three "independent" experiments contain the same 945 users. The overlap can bias the results.

### Conversion Experiment (Task 18)
- Conversion B is +9.6% higher than A, z-test p ≈ 0.035
- **SRM check failed** (chi-square p ≈ 0.001): the traffic split is not 50/50, which points to a possible splitting or logging bug
- Recommendation: do not roll out B yet. Fix the split, check revenue/ARPU, then re-run the test

## Tools
Python, pandas, NumPy, SciPy (stats), statsmodels, matplotlib, Jupyter Notebook

## Files
- `Product_Analytics_test_exercises.ipynb`: solution code for all calculations
- `Тестовое задание.docx`: Word document with answers to all 18 questions
- three CSV data files (see **Data**)

## How to Run
1. Install the libraries:
   `pip install pandas numpy scipy statsmodels matplotlib jupyter`
2. Put the three CSV files in the same folder as the notebook
3. Open and run `Product_Analytics_test_exercises.ipynb`

## Keywords
`product-analytics` `data-science` `statistics` `ab-testing` `hypothesis-testing` `t-test` `z-test` `mann-whitney` `chi-square` `srm` `retention` `mau` `dau` `conversion` `nps` `arpu` `cohort-analysis` `python` `pandas` `scipy` `statsmodels` `jupyter-notebook`
