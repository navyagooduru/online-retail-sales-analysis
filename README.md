# Online Retail Sales Analysis

End-to-end data analysis project on a UK-based online retailer's transactional data, using **Python, SQL, and Excel** to uncover revenue trends, customer behavior patterns, and operational insights.

## Problem Statement

The business needed to understand: which products and customers drive the most revenue, how sales trend over time, which markets matter most, and when customers are most active — the kind of foundational analysis a data analyst would be asked to deliver to inform marketing, inventory, and retention decisions.

## Dataset

- **Source:** kaggle Dataset
- **Size:** ~540,000 transactions
- **Period:** December 2010 – December 2011
- **Fields:** Invoice number, stock code, product description, quantity, invoice date, unit price, customer ID, country

> Note: the raw CSV is not included in this repo due to size — download it from the source above and place it in `data/online_retail.csv` to reproduce this analysis.

## Tools Used

- **Python (pandas, matplotlib, seaborn)** — data cleaning, feature engineering, visualization
- **SQL (SQLite)** — business question queries: joins, CTEs, aggregations, window-style analysis
- **Excel / Google Sheets** — interactive dashboard with pivot-style charts for non-technical stakeholders

## Project Workflow

1. **Data Cleaning** (`notebooks/01_data_cleaning.ipynb`)
   Handled missing values (25% missing CustomerID, handled via flagging rather than dropping), removed ~9,300 cancelled orders, fixed data types, removed duplicates, and engineered features (Revenue, date parts) for downstream analysis.

2. **SQL Analysis** (`notebooks/02_sql_analysis.ipynb`)
   Loaded cleaned data into SQLite and answered 9 business questions using SQL: revenue trends, top products, revenue by country, top customers, average order value, customer order distribution, peak activity days, recency analysis, and cancellation patterns.

3. **Python Visualizations** (`notebooks/03_python_visualizations.ipynb`)
   Built custom charts beyond standard dashboard tools: a dual-axis revenue trend with month-over-month growth rate, a customer order frequency distribution, and a day-of-week × hour activity heatmap.

4. **Excel/Google Sheets Dashboard**
   Built a 4-chart dashboard (monthly revenue trend, top 10 products, revenue share by country, top 10 customers) designed for a non-technical, stakeholder-facing view.

## Key Findings

- **Revenue grew sharply heading into the holiday season** — from £758K in August to £1.5M in November 2011, a 98% increase over four months, with November as the peak month.
- **34.4% of customers were one-time buyers**, while the remaining ~66% made repeat purchases — indicating a solid retention base but room to improve first-purchase conversion to repeat business.
- **The United Kingdom dominates revenue** at roughly 87% of total sales, indicating heavy market concentration and limited geographic diversification.
- **Order activity peaks on weekday late mornings to early afternoons (10am–3pm, Tue–Fri)**, with Saturday being notably quiet — suggesting promotional campaigns would perform best timed around weekday midday rather than weekends.
- A small number of products account for a disproportionate share of revenue, consistent with a typical Pareto distribution in retail sales.

## Dashboard Preview

*(Add a screenshot of your Excel/Google Sheets dashboard here — see instructions below)*
<img width="1343" height="626" alt="image" src="https://github.com/user-attachments/assets/1c1f3f73-0335-48ce-8a8f-5999d785806d" />
<img width="1362" height="722" alt="image" src="https://github.com/user-attachments/assets/ad4468fb-d24b-4ff4-8231-97d23799f77b" />


## Repository Structure

```
retail_project/
├── data/
│   ├── online_retail.csv              # raw data (not included, see Dataset section)
│   ├── online_retail_cleaned.csv      # cleaned dataset
│   ├── cancellations.csv              # separated cancelled orders
│   ├── retail.db                      # SQLite database
│   ├── results_*.csv                  # SQL query outputs
│   └── chart_*.png                    # exported Python visualizations
├── notebooks/
│   ├── 01_data_cleaning.ipynb
│   ├── 02_sql_analysis.ipynb
│   └── 03_python_visualizations.ipynb
└── README.md
```

## How to Reproduce

1. Clone this repo
2. Download the dataset and place it at `data/online_retail.csv`
3. Install dependencies: `pip install pandas numpy matplotlib seaborn`
4. Run the notebooks in order: `01_data_cleaning.ipynb` → `02_sql_analysis.ipynb` → `03_python_visualizations.ipynb`

## Author

Navya Gooduru — final-year Data Science student
[LinkedIn](https://linkedin.com/in/navya-gooduru-787129278) | [GitHub](https://github.com/navyagooduru)
