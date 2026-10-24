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
- Net return on completed loans (total payments received vs. amount funded) falls from +5.4% (grade A) to -9.2% (grade G). Grades E, F, and G lost money, and grade D roughly broke even.
- Implication: a lender could tighten approval or raise pricing on grades D-G, which together are about 25% of completed loans.

## Limitations
- Net return is a lifetime figure (total payments received vs. amount funded). It is not annualized and ignores payment timing and lender costs.
- Only completed loans (Fully Paid or Charged Off) are included. Recent loans that are still active are excluded, which can make recent years look worse than they are.
- Results are descriptive, not causal. I did not control for other factors like income or loan purpose.

## Status
In progress. Full dataset loaded into SQLite; starting exploratory analysis.
