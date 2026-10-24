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
- Net return by grade is distorted when recent loans are included, because most recent loans that have a final status are charge-offs. Restricting to 36-month loans issued through 2014, which have all had time to finish, every grade was profitable, with lifetime returns of about +8.8% to +10.7%.
- Within that cleaner sample, riskier grades did not earn higher returns than safer ones. Grades B-F all returned about 10%, while grade A returned 7.7%. The higher interest on risky loans roughly offset their higher charge-off rates.
![Charge-off rate vs. net return by grade](grade_chart.png)

## Limitations
- Net return is a lifetime figure (total payments received vs. amount funded). It is not annualized and ignores payment timing and lender costs.
- Only completed loans (Fully Paid or Charged Off) are included. Recent loans that are still active are excluded, which can make recent years look worse than they are.
- Results are descriptive, not causal. I did not control for other factors like income or loan purpose.
- Completed-loan results are biased toward early charge-offs for recent issue years, so conclusions about profitability are preliminary.
- The clean comparison covers only 36-month loans issued 2007-2014, so it may not reflect later years or economic conditions. Grade G has only 274 loans in that sample, so its result is less reliable. Returns are lifetime, not annualized, and exclude lender costs and taxes.

## Status
In progress. Full dataset loaded into SQLite; starting exploratory analysis.
