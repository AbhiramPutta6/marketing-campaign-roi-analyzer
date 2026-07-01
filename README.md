# Marketing Campaign ROI Analyzer

Analyzed 2,216 customer records to identify which marketing channels and campaigns deliver the most value — revealing that purchase volume alone is a misleading metric for budget decisions.

## Business Question

Which marketing channels and past campaigns deliver the most value, and where should the company focus its budget next quarter?

## Dataset

This project uses a customer-level marketing dataset containing 2,240 records, each representing one customer's demographics, purchase history across three channels (Web, Catalog, Store), spending across six product categories, and their response to five past marketing campaigns.

Key columns include: `Income`, `Education`, `Marital_Status`, the six `Mnt*` spend-by-category columns, the three `Num*Purchases` channel columns, and `AcceptedCmp1`–`AcceptedCmp5` (whether the customer accepted each past campaign).

The original, unmodified file is included as `marketing_campaign_RAW.csv`.

## Tools Used

- **Microsoft Excel** — data cleaning, Pivot Tables, calculated columns, `CORREL()` statistical analysis
- **Microsoft Power BI Desktop** — DAX calculated columns, interactive dashboard
- **GitHub** — version control and portfolio hosting

## Process

1. Removed 24 records with missing `Income` values, reducing the dataset from 2,240 to 2,216 clean rows.
2. Created a `TotalSpend` calculated column by summing all six product-spend categories per customer.
3. Built a Pivot Table comparing total purchase volume across Web, Catalog, and Store channels.
4. Ran a correlation analysis between each channel's purchase count and `TotalSpend`, to test which channel was most associated with high-value customers.
5. Tested `Income` as an alternative explanation for the Catalog finding, by correlating `Income` against both `TotalSpend` and Catalog purchases.
6. Built a Power BI dashboard, including a DAX calculated column (`PrimaryChannel`) that labels each customer by their most-used channel.
7. Visualized channel volume, average spend by primary channel, total customer count, and campaign acceptance rates.

## Key Findings

- **Store has the highest total purchase volume** (12,855), ahead of Web (9,053) and Catalog (5,919).
- **Despite this, Catalog purchases have the strongest correlation with total customer spend** (0.78), compared to Store (0.68) and Web (0.53).
- Customers whose primary channel is Catalog show a notably higher average total spend than Web or Store customers — nearly double in the dashboard comparison.
- **Income alone does not fully explain this pattern**: Income correlates with `TotalSpend` at 0.67 and with Catalog purchases at 0.59 — both weaker than Catalog's own 0.78 correlation with spend.
- Among past campaigns, **Campaign 4 had the highest customer acceptance rate**, while **Campaign 2 had the lowest**.

## Dashboard

![Marketing ROI Dashboard]dashboard_export_final.pdf

The full interactive file (`marketing_roi_dashboard.pbix`) and a static export (`dashboard_export_final.pdf`) are included in this repository.

## Recommendation

Even though the Store channel gets the most purchases, Catalog customers spend almost double on average — so next quarter, the company should invest more in Catalog marketing instead of assuming more purchases automatically means more value.

Separately, looking at past campaign performance, Campaign 4 had the highest customer acceptance while Campaign 2 had the lowest — suggesting the company should study what made Campaign 4 successful and apply similar strategies going forward, rather than repeating Campaign 2's approach.

## Limitations

This analysis is based on customer purchase and spending patterns rather than actual marketing spend, since cost-per-channel data wasn't available — so while shifting more budget toward Catalog is recommended, a follow-up analysis with real budget figures would confirm the actual return on investment before committing significant funds.
