# Credit Risk Analysis

Analyzing public loan data with SQL and Python to identify which borrower segments carry the highest default risk.

## Question
Which borrower segments carry the highest default risk, and how should a lender adjust pricing or approval criteria?

## Tools
- SQL (SQLite)
- Python (pandas, matplotlib)
- Tableau

## Data Notes
- Source: Lending Club loan data (2007-2018, about 2.26 million loans) from Kaggle.
- My first 100,000 rows were almost all active loans (about 97% "Current"), with only 19 charge-offs, so I loaded the full file into SQLite in chunks.
- I analyze only loans with a final outcome (Fully Paid or Charged Off), since active loans haven't finished yet.
- Completed loans are those with status Fully Paid or Charged Off (about 1.3 million). Active, late, and policy-exception loans are excluded.

## Findings
- Of about 1.3 million completed loans, roughly 20% were charged off.
- Charge-off rates rise steadily with loan grade, from 6.1% (grade A) to 50.1% (grade G).
- Grades B and C account for about 57% of completed loans.
- Net return by grade depends heavily on which loan years are included. Across all completed loans, grades E-G appear to lose money, but this is distorted by recent loans that are mostly still active. Restricting to loans issued through 2014, all grades were profitable (about +8% to +13% lifetime return).

## Limitations
- Net return is a lifetime figure (total payments received vs. amount funded). It is not annualized and ignores payment timing and lender costs.
- Only completed loans (Fully Paid or Charged Off) are included. Recent loans that are still active are excluded, which can make recent years look worse than they are.
- Results are descriptive, not causal. I did not control for other factors like income or loan purpose.
- Completed-loan results are biased toward early charge-offs for recent issue years, so conclusions about profitability are preliminary.

## Status
In progress. Full dataset loaded into SQLite; starting exploratory analysis.
