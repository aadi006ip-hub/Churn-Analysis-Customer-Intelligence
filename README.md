# 📊 Churn Analysis and Customer Intelligence 

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![SQLite](https://img.shields.io/badge/SQLite-Database-lightgrey.svg)
![Data Analysis](https://img.shields.io/badge/Data-Analytics-success.svg)
![Business Intelligence](https://img.shields.io/badge/Business-Intelligence-orange.svg)

## 📝 Project Overview & Business Context
In the hyper-competitive OTT landscape (e.g., Netflix, Hotstar, Prime), customer retention is the only way to survive[span_0](start_span)[span_0](end_span). This project serves as an end-to-end data analytics pipeline designed to identify high-risk subscribers using a multi-dimensional dataset encompassing customer demographics, subscription tiers, and support escalations[span_1](start_span)[span_1](end_span).

Fundamentally, this churn analysis focuses on three core questions:
*   **"Who"**: Identifying which customers left or will leave in the future[span_2](start_span)[span_2](end_span).
*   **"Why"**: Analyzing their behavior before they left[span_3](start_span)[span_3](end_span).
*   **"When"**: Finding the "danger zone"—the point when a user leaves[span_4](start_span)[span_4](end_span).

While built on streaming data (where churn is defined as an inactive membership), this portfolio-ready project is highly applicable to other industries including **SaaS** (canceled subscriptions), **E-commerce** (no purchase in 90 days), **Telecom**, **Banking**, and **Adtech**[span_5](start_span)[span_5](end_span).

**Author / Project Inspiration:** Rishabh Mishra[span_6](start_span)[span_6](end_span)

---

## 🛠️ Detailed Methodology & Tech Stack
This project bridges the gap between technical execution and executive reporting. 

### 1. Data Pipeline & Extraction
*   **Tools:** Python, `pandas`, `sqlite3`[span_7](start_span)[span_7](end_span).
*   **Process:** Connected the SQL database directly to Python to pull multi-table datasets using SQL queries[span_8](start_span)[span_8](end_span).

### 2. Data Cleaning & Feature Engineering
*   **Tools:** `numpy`, `pandas`[span_9](start_span)[span_9](end_span).
*   **Process:** Handled missing/null values, corrected data types, and executed quality checks[span_10](start_span)[span_10](end_span). Created new calculated columns, applied data transformations, and calculated metrics like customer tenure, churn rates, and aging[span_11](start_span)[span_11](end_span).

### 3. Exploratory Data Analysis (EDA) & Visualization
*   **Tools:** `pandas`, `matplotlib`, `seaborn`[span_12](start_span)[span_12](end_span).
*   **Process:** Conducted aggregations, group-by operations, and pivot tables to summarize data[span_13](start_span)[span_13](end_span). Built behavioral visualizations to translate technical findings into actionable, billion-dollar business insights[span_14](start_span)[span_14](end_span).

---

## 🗄️ Database Architecture (`customer_churn`)
The analysis seamlessly joins three distinct relational tables[span_15](start_span)[span_15](end_span):

| `db_customer` (Demographics) | `db_subscription` (Financials) | `db_support` (Interactions) |
| :--- | :--- | :--- |
| `customerid` | `customerid` | `customerid` |
| `name`, `gender`, `dob` | `subscription_start_date`, `subscription_type`| `complaint_date` |
| `country`, `State`, `pincode`| `renewal_date`, `contract_type`, `plan_type` | `Escalations` |
| `interests` | `cancellation_date`, `cancellation_reason` | `csat score` |
| | `monthly_charges`, `cltv`, `churn_score` | `comment` |

---

## 🔬 Core Analytical Modules

### Module 1: Risk Scoring & Segmentation
Developed a multi-dimensional churn risk scoring model by synthesizing subscription tenure, plan type, and support escalation signals across the three tables (tracking 20+ KPIs)[span_16](start_span)[span_16](end_span). The customer base was segmented into risk tiers using composite churn scores, exposing a massive lifetime value (LTV) gap between churned and retained cohorts[span_17](start_span)[span_17](end_span).

### Module 2: Support Intelligence & Cancellation Analysis
Performed cross-functional correlation analysis by joining complaint, escalation, and CSAT data with subscription records[span_18](start_span)[span_18](end_span). 
*   **Key Finding:** Escalated support interactions were disproportionately concentrated among churned customers[span_19](start_span)[span_19](end_span). 
*   **Driver Deconstruction:** Decomposed cancellation drivers into competitor switching, pricing sensitivity, and content dissatisfaction[span_20](start_span)[span_20](end_span).

### Module 3: Churn & Revenue Impact
Engineered the pipeline to quantify exactly how much revenue was leaking[span_21](start_span)[span_21](end_span). Uncovered significant churn disparities between monthly and annual contract segments and delivered a data-backed contract-migration strategy to reduce involuntary subscriber loss[span_22](start_span)[span_22](end_span).

---

## 💡 Executive Insights & Financial Impact
*   **Overall Health:** The platform currently has a **28.6% Churn Rate** (71.4% Retention Rate)[span_23](start_span)[span_23](end_span). Average customer tenure is 1,451 days, with an ARPU of Rs 18.8[span_24](start_span)[span_24](end_span).
*   **The Contract Disparity:** Monthly-contract subscribers churned at an alarming **55.6%**, which is 6.7 times higher than the **8.3%** annual-contract rate[span_25](start_span)[span_25](end_span). 
*   **Quantified Losses:** This churn directly attributed to $73.94/mo in MRR (Monthly Recurring Revenue) leakage and a $2,047 erosion in CLTV (Customer Lifetime Value)[span_26](start_span)[span_26](end_span). Total revenue loss sits at 18%[span_27](start_span)[span_27](end_span).
*   **Demographic & Temporal Trends:** Peak churn occurred in **September 2024**, with **Karnataka** acting as the most affected state[span_28](start_span)[span_28](end_span). The vast majority of churn originates from the Basic subscription plan[span_29](start_span)[span_29](end_span).

---

## 🎯 Action Items & Growth Strategy
Based on the data, the following next steps are recommended for the platform's growth team:

1.  **Investigate Localized Anomalies:** Immediately check what occurred in Karnataka during September 2024. Was there a localized tech issue, an increase in user complaints, or a price hike for the Basic plan?[span_30](start_span)[span_30](end_span)
2.  **Competitor Defense:** Users are actively migrating to competitors. Conduct a thorough analysis of competitor pricing and content offerings[span_31](start_span)[span_31](end_span).
3.  **Prioritized Intervention:** Focus on customers tagged with 'High' & 'Med' churn risk[span_32](start_span)[span_32](end_span). Rank them by their LTV to create a priority outreach list[span_33](start_span)[span_33](end_span). Actively resolve their complaint requests via targeted email, SMS, and calls[span_34](start_span)[span_34](end_span).
4.  **Strategic Migration:** Prioritize retaining Premium annual-plan users over acquiring Basic monthly users to maximize long-term revenue yield[span_35](start_span)[span_35](end_span).

---
