
Project 2: Cohort Retention & Customer Lifetime Value (CLTV) Analysis

Infotact Solutions — Data Analytics Internship

📌 Objective
E-commerce/SaaS businesses lose more money to churn than they gain from new signups. This project performs a deep-dive Cohort Analysis to understand user retention behaviour and calculates Customer Lifetime Value (CLTV) to identify high-value vs. low-value customer segments, enabling data-backed retention and acquisition decisions.

🗂️ Repository Structure

├── Data/
│   ├── Row/                          # raw input data (NOT pushed — see .gitignore)
│   │   ├── transactions_raw.csv
│   │   └── user_profiles.csv
│   └── processed/                    # cleaned/derived data (NOT pushed — see .gitignore)
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
│   ├── 01_EDA_Cleaning.ipynb          # Week 1 — Data Cleaning
│   ├── 02_Cohort_Matrix.ipynb         # Week 2 — Cohort Matrix + Retention Heatmap
│   └── 03_CLTV_Calculation.ipynb      # Week 3 — CLTV + Segment Analysis
├── Output/
│   ├── monthly_transactions.png
│   ├── acquisition_channel.png
│   ├── region_distribution.png
│   └── retention_heatmap.png          # NEW — Cohort Retention Heatmap
├── Reports/
│   └── Executive_Summary_Report.docx
├── CLTV_Dashboard.pbix                # Week 4 — Power BI Dashboard
└── README.md

⚠️ Raw and processed .csv files are excluded from GitHub via .gitignore per program data-privacy guidelines. To reproduce, place transactions_raw.csv and user_profiles.csv in Data/Row/ and run the notebooks in order (01 → 02 → 03).

🔧 Tech Stack

Python (Pandas, NumPy, Matplotlib, Seaborn) · Jupyter Notebook · Power BI (DAX)

📅 Four-Week Roadmap — Final Status

Week	                     Task	                                                                                Status
1                          Data cleaning — remove failed transactions, calculate cohort month	                  ✅ Done
2	                         Cohort retention matrix (absolute + %)	                                              ✅ Done
2                          Retention Heatmap visualization (Seaborn)	                                          ✅ Done — added and verified
3	                         AOV, Purchase Frequency, Historical CLTV (per customer)	                            ✅ Done
3	                         Segment-wise CLTV (by Region & Acquisition Channel)	                                ✅ Done — added and verified
4	                         Interactive Power BI dashboard	                                                      ✅ Done

🔍 Methodology

Week 1 — Cleaning (01_EDA_Cleaning.ipynb): Loaded raw transactions and user profiles; removed failed status rows, leaving 2,211 completed transactions from 1,546 paying customers. Calculated each user's cohort_month (month of first transaction) and exported cleaned_transactions.csv and first_purchase.csv.

Week 2 — Cohort Matrix & Heatmap (02_Cohort_Matrix.ipynb):

Grouped transactions by cohort_month and months_since_acquisition using groupby + pivot_table to build the absolute retention matrix (cohort_pivot).
Normalized by each cohort's initial size to get % retention (retention_matrix), with Month 0 = 100% baseline.
Added a Seaborn heatmap (sns.heatmap) visualizing the full retention decay pattern across all 16 monthly cohorts (Jan 2023–Apr 2024) and up to 7 months of follow-up, saved as retention_heatmap.png.
Exported cohort_pivot.csv and retention_matrix.csv.

Week 3 — CLTV & Segmentation (03_CLTV_Calculation.ipynb):

Calculated per-customer Average Order Value (AOV), Purchase Frequency, and Historical CLTV (AOV × Frequency).
Identified Top 10 customers by CLTV.
Built region_summary and channel_summary (revenue + customer count by segment).
Added segment-level average CLTV — grouped by region and acquisition_channel separately — to directly compare customer value across geography and marketing source (segment_cltv_region.csv, segment_cltv_channel.csv).

Week 4 — Dashboard: Built an interactive Power BI dashboard (CLTV_Dashboard.pbix) — Total Revenue, Total Customers, Average Order Value, Average CLTV, Top 10 Customers by CLTV, Revenue by Region, Revenue by Acquisition Channel, and Customer Distribution by Region — with slicers for Region and Acquisition Channel.

📊 Key Business Insights
Retention drops sharply after Month 0. Across cohorts, retention falls from 100% to roughly 14–20% by Month 1, and continues to decline gradually through Month 7 — most churn happens in the first 30 days. This is clearly visible in retention_heatmap.png.
South region generates the highest revenue (₹15.1L) and also the highest average CLTV (₹4,720.71) among all regions.
East region has the lowest customer count (269 customers) and lowest average CLTV (₹4,548.97) — a candidate for targeted acquisition campaigns, since per-customer value isn't the issue — volume is.
TikTok drives the highest average CLTV per customer (₹4,897.69), followed by Meta Facebook (₹4,654.74), while Organic-acquired customers have the lowest average CLTV (₹4,381.13) despite being a "free" channel — suggesting paid social attracts higher-intent buyers.
Total portfolio: ₹70.7L total revenue, 1,546 paying customers, ₹3,227 average order value, ₹4,580 average CLTV.
Top 10 customers contribute disproportionately to total CLTV (led by a single customer at ₹12.2K), reinforcing the value of VIP retention programs.

✅ Recommendation
Since Month 1 is the biggest drop-off point, an automated re-engagement email sequence targeting customers at the 30-day mark — combined with region-specific acquisition efforts for East and channel-specific budget reallocation toward TikTok/Meta — is the most direct lever to raise overall CLTV.

📎 Related Files
Reports/Executive_Summary_Report.docx — full business insights report with dashboard screenshot
CLTV_Dashboard.pbix — open in Power BI Desktop to explore interactively

🔗 Links
GitHub Repository: github.com/poonambokde/Project2-Cohort-Retention-CLTV

👩‍💻 Author

Poonam Bokade Data Analytics Intern, Infotact Solutions | B.Tech Computer Engineering

