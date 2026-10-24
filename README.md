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

## Status
In progress. Full dataset loaded into SQLite; starting exploratory analysis.
