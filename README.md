
#  Banking Customer Data Analysis — Data Analytics Project



---

## 📋 Table of Contents

1. [Business Problem Statement]
2. [Project Overview]
3. [Dataset Description]
4. [Project Structure]
5. [Tools & Technologies]
6. [Exploratory Data Analysis (EDA)]
7. [Key Insights & Findings]
8. [Dashboard Highlights]
9. [Conclusion & Recommendations]

---

## 🎯 Business Problem Statement

Banks today manage thousands of diverse customers with varying financial behaviors, income levels, risk profiles, and loyalty standings. Without a structured understanding of these customer segments, it becomes difficult to:

- **Identify high-value customers** who contribute disproportionately to revenue.
- **Detect customers at risk** of churn or financial distress.
- **Optimize product offerings** such as loans, credit cards, and business lending.
- **Tailor fee structures** and loyalty programs to retain profitable customer segments.
- **Assess portfolio risk** across different demographics and geographies.

**This project aims to answer the following business questions:**

> 1. What is the financial profile of the bank's customer base — in terms of income, savings, loans, and credit usage?
> 2. How do loyalty tier and fee structure vary across customer demographics (nationality, occupation, age)?
> 3. What correlations exist between financial variables like income, deposits, loans, and business lending?
> 4. Which customer segments carry the highest risk weighting, and what does that mean for the bank's risk exposure?
> 5. How can the bank better segment customers to personalize financial products and improve loyalty outcomes?

By performing a thorough Exploratory Data Analysis (EDA) and building an interactive Power BI dashboard, this project provides **data-driven insights** to help bank stakeholders make informed strategic decisions around customer retention, product cross-selling, and risk management.

---

## 📌 Project Overview

| Attribute | Detail |
|-----------|--------|
| **Domain** | Banking / Financial Services |
| **Project Type** | Exploratory Data Analysis (EDA) + Business Intelligence Dashboard |
| **Dataset Size** | 3,000 customers, 25 features |
| **Tools Used** | Python (Pandas, Seaborn, Matplotlib), Power BI |
| **Deliverables** | Jupyter Notebook (EDA) + Power BI Dashboard (.pbix) |

---

## 📊 Dataset Description

The dataset contains **3,000 banking customer records** with **25 features** covering demographics, financial holdings, product usage, and loyalty classification.

### Features at a Glance

| Category | Columns |
|----------|---------|
| **Identity** | Client ID, Name |
| **Demographics** | Age, Nationality, Location ID, GenderId |
| **Occupation & Contact** | Occupation, Banking Contact |
| **Account Info** | Joined Bank, BRId, IAId |
| **Financial Products** | Amount of Credit Cards, Credit Card Balance, Bank Loans, Bank Deposits, Checking Accounts, Saving Accounts, Foreign Currency Account, Business Lending, Superannuation Savings |
| **Classification** | Fee Structure, Loyalty Classification, Risk Weighting, Properties Owned |
| **Income** | Estimated Income |

## Key Statistics

| Metric | Value |
|--------|-------|
| Total Customers | 3,000 |
| Age Range | 17 – 85 years (Mean: ~51 years) |
| Estimated Income Range | ₹15,919 – ₹5,22,330 (Mean: ~₹1,71,305) |
| Avg. Business Lending | ~₹8,66,760 |
| Avg. Bank Deposits | — |
| Credit Cards Held | 1 (64%), 2 (25.5%), 3 (10.5%) |

## Categorical Distributions

- **Loyalty Classification:** Jade (44.4%) > Silver (25.6%) > Gold (19.5%) > Platinum (10.6%)
- **Fee Structure:** High (49.2%) > Mid (32.1%) > Low (18.7%)
- **Nationality:** European (43.6%) > Asian (25.1%) > American (16.9%) > Australian (8.5%) > African (5.9%)
- **Risk Weighting:** Levels 1–5, with Level 2 being most common (40.7%)
- **Properties Owned:** Roughly equal distribution across 0, 1, 2, and 3 properties

---

## 📁 Project Structure

```
Banking-Customer-Analysis/
│
├── 📂 data/
│   └── Banking.csv                    # Raw dataset (3,000 records, 25 features)
│
├── 📂 notebooks/
│   └── final_banking_EDA.ipynb        # Jupyter Notebook with full EDA
│
├── 📂 dashboard/
│   └── final_banking_dashboard.pbix   # Power BI interactive dashboard
│
└── README.md                          # Project documentation (this file)
```

---

## 🛠 Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Python 3.x** | Core analysis language |
| **Pandas** | Data loading, cleaning, and transformation |
| **NumPy** | Numerical operations |
| **Matplotlib** | Base plotting library |
| **Seaborn** | Statistical data visualization |
| **Power BI** | Interactive business intelligence dashboard |
| **Jupyter Notebook** | Development environment for EDA |

---

## 🔍 Exploratory Data Analysis (EDA)

The EDA was performed in `final_banking_EDA.ipynb` and covers the following stages:

## 1. Data Loading & Initial Inspection
- Loaded the dataset using Pandas
- Inspected shape, data types, and null values using `.info()`, `.describe()`, and `.head()`

## 2. Feature Engineering
- Created an **Income Band** feature by binning `Estimated Income` into:
  - **Low** (< ₹1,00,000)
  - **Medium** (₹1,00,000 – ₹3,00,000)
  - **High** (> ₹3,00,000)

## 3. Univariate Analysis
- Plotted distributions of all categorical columns using `sns.countplot()`
- Plotted histograms with KDE for all key numerical columns: Age, Estimated Income, Superannuation Savings, Credit Card Balance, Bank Loans, Bank Deposits, Saving Accounts, Business Lending

## 4. Bivariate Analysis
- Used Nationality as a `hue` variable across all categorical features to understand cross-demographic patterns

## 5. Correlation Analysis
- Generated a **correlation heatmap** for 8 core financial variables

---

##  Key Insights & Findings

## Financial Behavior Correlations

The correlation analysis revealed important relationships among financial variables:

| Variable Pair | Correlation | Insight |
|---|---|---|
| Bank Deposits ↔ Saving Accounts | **0.75** (Strong) | Customers with high deposits also maintain high savings |
| Estimated Income ↔ Superannuation Savings | 0.37 (Moderate) | Higher earners save more for retirement |
| Estimated Income ↔ Bank Loans | 0.33 (Moderate) | Higher income customers take more loans |
| Estimated Income ↔ Business Lending | 0.33 (Moderate) | Wealthier customers utilize business credit |
| Business Lending ↔ Bank Deposits | 0.44 (Moderate) | Business borrowers tend to also deposit more |
| Business Lending ↔ Bank Loans | 0.42 (Moderate) | Heavy bank product users cluster together |
| Credit Card Balance ↔ Bank Deposits | 0.38 (Moderate) | Higher card users also deposit more |
| Age ↔ All Financial Variables | ~0.00 (Negligible) | Age is not a predictor of financial activity |

> **Key Takeaway:** Age is not a meaningful segmentation variable for this bank's customers. Financial behavior is better explained by income, deposits, and product engagement.

### Customer Segmentation Observations

- **Jade loyalty tier** dominates the customer base, indicating most customers are at entry/basic loyalty level — a growth opportunity for the bank to upsell to Silver, Gold, or Platinum.
- **High fee structure** customers represent the largest segment (49.2%), showing the bank skews toward premium pricing.
- **European nationals** make up the largest customer group, followed by Asian customers — useful for culturally tailored product marketing.
- Most customers hold **only 1 credit card**, suggesting potential for cross-selling additional credit products.
- **Risk Level 2** is the most common, indicating a moderately low-risk portfolio overall.

---

## 📈 Dashboard Highlights

The Power BI dashboard (`final_banking_dashboard.pbix`) provides an **interactive, visual summary** of the analysis with the following components:

- **Customer Demographics Overview** — Age distribution, nationality breakdown, gender split
- **Financial Portfolio Summary** — Income bands, bank deposits, loan values, savings comparisons
- **Loyalty & Fee Structure Analysis** — Loyalty tier distribution by nationality and occupation
- **Risk Profiling** — Risk weighting distribution and its relationship to financial holdings
- **Product Usage Analysis** — Credit card counts, foreign currency accounts, business lending trends
- **Slicers & Filters** — Dynamic filtering by nationality, occupation, loyalty tier, and fee structure

> **To view the dashboard:** Open `final_banking_dashboard.pbix` in [Microsoft Power BI Desktop](https://powerbi.microsoft.com/en-us/desktop/) (free download).

---

## ✅ Conclusion & Recommendations

### Conclusions

1. The bank's customer base is **financially diverse** but skews toward moderate-to-high income earners with consistent deposit behavior.
2. **Income and product engagement** (not age) are the primary drivers of financial activity across the customer base.
3. The strong deposit-savings correlation suggests a **loyal, savings-oriented core segment** that may respond well to wealth management products.
4. The majority of customers sitting in the **Jade loyalty tier** represents a large addressable segment for loyalty program upgrades.

### Business Recommendations

| Recommendation | Rationale |
|---|---|
| **Cross-sell business lending to high-deposit customers** | Strong correlation (0.44) between deposits and business lending |
| **Upgrade Jade-tier customers with targeted loyalty incentives** | 44% sit at the lowest tier — high upsell potential |
| **Offer superannuation and retirement products to high-income customers** | Income-superannuation correlation of 0.37 |
| **Launch credit card bundle campaigns for single-card holders** | 64% of customers hold only 1 card |
| **Develop risk-adjusted product tiers** | Align product offerings with Risk Weighting scores (1–5) |
| **Nationality-targeted marketing campaigns** | European and Asian segments dominate — culturally relevant messaging |

---

 ## Author

**[Partha Sarathi Yadav]


📧 [yadavparthasarathi9@gmail.com]
🔗 [LinkedIn -  https://www.linkedin.com/in/partha-sarathi-yadav-135b60291]
🐙 [GitHub Profile URL - https://github.com/yadavparthasarathi9-del]

---
