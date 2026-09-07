# Decoding Customer Value: A SQL-Driven Retention Strategy

**Consulting & Analytics Club, IIT Guwahati — Summer Projects '26**
End-to-end customer intelligence project for a D2C fashion brand: Python feature engineering, SQL segmentation, and a Power BI dashboard to separate genuine customer loyalty from discount-driven demand.


## The Business Problem

A direct-to-consumer fashion brand with ~3,900 customers has no loyalty score, no churn label, and no timestamps in its data — every concept used here (loyalty, value tier, promo dependency) is engineered from raw transactional and behavioral variables, not assumed.

**Core question:** Is the business building a genuinely loyal customer base, or is it reliant on continuous promotional activity — and what should it do under either scenario?



## Approach

1. **Python — Data Cleaning & Feature Engineering** (`Python_Jupyter_Notebook.ipynb`)
   Built customer-level metrics from the raw dataset (`Dataset.csv`) — including a value score, discount-dependency score, and satisfaction flag — with the reasoning behind each metric explained inline. Output saved as `Cleaned Data.csv` / `Cleaned Data.xlsx`.

2. **SQL — Segmentation & Analysis** (`SQL Queries.ipynb`, outputs in `SQL Outputs.zip`)
   Ten structured queries (q1–q10) answering the five core business questions: who the high-value vs. low-value customers are, which categories/seasons associate with tenure, which geographies show organic vs. discount-driven demand, and who the ideal customer profile is.

3. **Power BI — Founder Dashboard** (`PowerBIDashboard.pbix`)
   Four-panel dashboard built for a non-technical founding team: customer value pyramid, promo dependency vs. retention, geographic opportunity map, and category funnel.

4. **Retention Playbook & Executive Summary** (`Retention_Playbook.docx`, `Executive_Summary.docx`)
   Translated the analysis into two concrete, actionable outputs: a promotional sunset plan and an ideal customer profile (ICP), each with a named trigger, timeline, and success metric.



## Key Findings

- **6.4% of the customer base** already represents the brand's ideal profile: high spend, high tenure, high satisfaction, and no discount dependency.
- The promotional program is **not** converting bargain hunters into more loyal buyers than full-price customers already are.
- **270 low-tenure, full-discount customers** are the lowest-risk segment to test a promotional pullback on (avg. value score 266 vs. brand average 1,505).
- **51 high-tenure, high-value subscribers** are deliberately excluded from any discount sunset — the relationship risk outweighs the ~$814 margin recovery.
- Fall is the season with the **lowest promo dependency (0.81)** and **highest full-price purchase rate (59.3%)** — the best window for no-discount acquisition campaigns.



## Recommendations

**1. Promotional Sunset Test**
Run a 50% discount reduction as an A/B test on the 270-customer low-tenure, full-discount segment.
- Month 1–2: launch test (Test vs. Control)
- Month 3: compare repeat purchase rates
- Month 4: roll out fully if Test stays within 5pp of Control; revert if it drops more than 10pp
- Estimated impact: ~$1,592/cycle at 50% reduction, up to ~$3,184/cycle if full removal succeeds

**2. Ideal Customer Profile (ICP) Targeting**
The ICP: a 40–50 year-old professional, buying Clothing at full price roughly monthly, ~$80/order, 35–45 prior purchases, 4.5/5 rating — concentrated in Arizona, Michigan, Nevada, and New Mexico.
- Build lookalike audiences from the 251 identified ICP customers
- Run no-discount brand campaigns in Fall
- Reposition Outerwear as a post-purchase upsell (highest ICP spend at $82.67, but lowest ICP volume at 8.4%)

Full reasoning and trade-offs for each recommendation are in [`Retention_Playbook.docx`](./Retention_Playbook.docx) and [`Executive_Summary.docx`](./Executive_Summary.docx).



## Repository Contents

| File | Description |
|---|---|
| `Dataset.csv` | Raw source data |
| `Python_Jupyter_Notebook.ipynb` | Data cleaning + feature engineering |
| `Cleaned Data.csv` / `Cleaned Data.xlsx` | Output of the cleaning/feature engineering step |
| `SQL Queries.ipynb` | Segmentation queries (q1–q10) |
| `SQL Outputs.zip` | Query result CSVs |
| `PowerBIDashboard.pbix` | Interactive 4-panel founder dashboard |
| `Executive_Summary.docx` | 1-page summary of findings and recommendations |
| `Retention_Playbook.docx` | Full promotional sunset plan + ideal customer profile |

## How to Reproduce

1. Run `Python_Jupyter_Notebook.ipynb` on `Dataset.csv` to generate the cleaned data with engineered features.
2. Run `SQL Queries.ipynb` against the cleaned data to reproduce the q1–q10 outputs (also available pre-run in `SQL Outputs.zip`).
3. Open `PowerBIDashboard.pbix` in Power BI Desktop to explore the interactive dashboard.
