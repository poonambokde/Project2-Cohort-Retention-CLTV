Project 2: Cohort Retention & Customer Lifetime Value (CLTV) Analysis

Infotact Solutions — Data Analytics Internship (4-Week Sprint)

📌 Objective

E-commerce/SaaS businesses lose more money to churn than they gain from new signups. This project performs a deep-dive Cohort Analysis to understand user retention behaviour and calculates Customer Lifetime Value (CLTV) to identify high-value vs. low-value customer segments, enabling data-backed retention and acquisition decisions.

Repository Structure

├── Data/
│   ├── Row/                        # raw input data (NOT pushed — see .gitignore)
│   │   ├── transactions_raw.csv
│   │   └── user_profiles.csv
│   └── processed/                  # cleaned/derived data (NOT pushed — see .gitignore)
│       ├── cleaned_transactions.csv
│       ├── first_purchase.csv
│       ├── cohort_pivot.csv
│       ├── retention_matrix.csv
│       ├── customer_cltv.csv
│       ├── region_summary.csv
│       ├── channel_summary.csv
│       ├── segment_cltv_region.csv
│       └── segment_cltv_channel.csv
├── Notebooks/
│   ├── 01_EDA_Cleaning.ipynb        # Week 1
│   ├── 02_Cohort_Matrix.ipynb       # Week 2
│   └── 03_CLTV_Calculation.ipynb    # Week 3
├── Output/
│   ├── monthly_transactions.png
│   ├── acquisition_channel.png
│   ├── region_distribution.png
│   └── retention_heatmap.png
├── CLTV_Dashboard.pbix              # Week 4 — Power BI Dashboard
└── README.md

aw and processed .csv files are excluded from GitHub via .gitignore per program data-privacy guidelines. To reproduce, place transactions_raw.csv and user_profiles.csv in Data/Row/ and run the notebooks in order (01 → 02 → 03).

Tech Stack

Python (Pandas, NumPy, Matplotlib, Seaborn) · Jupyter Notebook · Power BI (DAX)

Four-Week Roadmap

Week	Task	Status
1	Data cleaning — remove failed transactions, calculate cohort month	✅
2	Cohort retention matrix (absolute + %) + heatmap visualization	✅
3	AOV, Purchase Frequency, Historical CLTV, segment-wise CLTV (region/channel)	✅
4	Interactive Power BI dashboard	✅

Methodology

Week 1 — Cleaning: Loaded 3,340 raw transactions across 2,000 users; removed failed status rows, leaving 2,211 completed transactions from 1,546 paying customers. Calculated each user's cohort_month (month of first transaction).

Week 2 — Cohort Matrix: Grouped transactions by cohort_month and months_since_acquisition using groupby + pivot_table to build the absolute retention matrix, then normalized by initial cohort size to get % retention (Month 0 = 100% baseline).

Week 3 — CLTV: Calculated per-customer Average Order Value (AOV), Purchase Frequency, and Historical CLTV (AOV × Frequency). Extended this to segment-level CLTV by region and acquisition channel to compare customer value across marketing sources.

Week 4 — Dashboard: Built an interactive Power BI dashboard (Total Revenue, Total Customers, Average CLTV, Top 10 Customers, Revenue by Region/Channel) with slicers for Region and Acquisition Channel.

Key Business Insights
Retention drops sharply after Month 0. Across cohorts, retention falls from 100% to roughly 14–20% by Month 1, and continues to decline gradually through Month 7 — most churn happens in the first 30 days.
South region generates the highest revenue (₹15.1L) and also the highest average CLTV (₹4,720.71) among all regions.
East region has the lowest customer count (269 customers) and lowest average CLTV (₹4,548.97) — a candidate for targeted acquisition campaigns.
TikTok drives the highest average CLTV per customer (₹4,897.69), followed by Meta Facebook (₹4,654.74), while Organic-acquired customers have the lowest average CLTV (₹4,381.13) despite being a "free" channel — suggesting paid social attracts higher-intent buyers.
Total portfolio: ₹70.7L total revenue, 1,546 paying customers, ₹3,227 average order value, ₹4,580 average CLTV.
Top 10 customers contribute disproportionately to total CLTV (led by a single customer at ₹12.2K), reinforcing the value of VIP retention programs.


✅ Recommendation

Since Month 1 is the biggest drop-off point, an automated re-engagement email sequence targeting customers at the 30-day mark — combined with region-specific offers for East and channel-specific budget reallocation toward TikTok/Meta — is the most direct lever to raise overall CLTV.

Part of the Infotact Solutions Advanced Data Analytics Internship Program (2026).




