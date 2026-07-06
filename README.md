# 📊 Advanced Customer Intelligence & Churn Optimization Framework
This repository delivers a production-grade data analytics pipeline and customer intelligence framework designed for modern subscription-based platforms. The architecture, methodologies, and business insights implemented here are built in accordance with the specifications outlined in **Data Analytics Project -Churn Analysis Report.pdf**.
## 👔 Business Case & Strategy
In hyper-competitive subscription landscapes (such as OTT streaming platforms like Netflix, Hotstar, and Prime), customer acquisition is only half the battle—sustained retention drives survival and long-term valuation. This framework addresses subscription vulnerabilities by breaking down customer attrition into three fundamental layers:
 * **The "Who":** Pinpointing precise customer cohorts that have left or demonstrate a high probability of impending departure.
 * **The "Why":** Analyzing behavioral signals, dissatisfaction drivers, and operational bottlenecks prior to customer exit.
 * **The "When":** Identifying the "danger zone"—the structural timeline thresholds where user engagement drops and churn risks peak.
> **Cross-Industry Scalability:** While validated against an OTT streaming environment (where churn equals an inactive membership), the underlying relational queries and analytics modules are intentionally built to port directly into **SaaS** (subscription cancellations), **E-Commerce** (90-day purchase latency), **Telecom** (account terminations), and **Fintech** (transactional dormancy).
> 
## 🛠️ Tech Stack & Engineering Pipeline
The pipeline bypasses heavy enterprise overhead by using a highly optimized, single-node Python and SQL stack engineered for rapid data processing and exploratory analysis:
 * **Database Engine:** sqlite3 for local relational data storage and extraction.
 * **Data Processing & Transformation:** pandas and numpy for multi-table merges, schema validation, and high-performance vectorized operations.
 * **Statistical Visualization:** matplotlib and seaborn for behavioral modeling and plotting risk distributions.
### Architectural Milestones
 1. **Relational Data Extraction:** Programmatic database connections executing multi-table joins to pull disparate user records into unified analytical dataframes.
 2. **Quality Control & Structural Cleaning:** Standardizing schema data types, resolving null/missing vectors, and executing automated QC checks across records.
 3. **Advanced Feature Engineering:** Calculating exact customer tenure, dynamic customer aging vectors, and time-weighted risk scores.
 4. **Behavioral EDA & Visual Reporting:** Generating multi-dimensional pivot matrices, aggregations, and visual assets to translate technical indicators into executive-level growth strategies.
## 🗄️ Relational Database Architecture
The analytical pipeline ingests data across three relational schemas via the core customer_churn database:
### 1. Demographics (db_customer)
Contains the foundational user vectors utilized for geographic and demographic segmentation:
 * customerid (Primary Key)
 * name | gender | dob
 * country | State | pincode
 * interests
### 2. Financials & Subscriptions (db_subscription)
Tracks core financial metrics, contract terms, and historical revenue tracking:
 * customerid (Foreign Key)
 * subscription_start_date | renewal_date | cancellation_date
 * subscription_type | plan_type (Basic / Standard / Premium) | contract_type
 * cancellation_reason | monthly_charges | cltv | churn_score
### 3. Customer Operations (db_support)
Captures downstream friction points and post-purchase support interactions:
 * customerid (Foreign Key)
 * complaint_date | Escalations | csat score
 * comment
## 🧮 Operational KPIs & Analytics Formulas
The framework tracks and calculates over 20 distinct KPIs. Core business metrics computed within the source data pipeline include:
| Key Performance Indicator | Analytical Logic / Formula | Target Application |
|---|---|---|
| **Churn Rate** | Churned Customers / Total Customers | Baseline Retention Tracking |
| **Retention Rate** | 1 - Churn Rate | Platform Stability Metric |
| **ARPU (Avg Revenue Per User)** | SUM(Monthly Charges) / COUNT(Active Customer IDs) | Unit Economics Assessment |
| **Average Customer Tenure** | AVG(DATEDIFF(Cancellation Date OR NOW(), Subscription Start Date)) | Customer Lifetime Mapping |
| **Revenue at Risk** | SUM(Monthly Charges) WHERE Churn Score > 70 | Proactive Revenue Loss Mitigation |
| **Escalation Rate** | (SUM(Escalations) / COUNT(Complaints)) * 100 | Support Efficiency & Friction Audit |
| **Avg Complaints Per User** | COUNT(Complaints) / COUNT(DISTINCT Customer ID) | Product Friction Diagnostics |
## 📈 Executive Executive Insights & Financial Findings
Analysis of the underlying platform data revealed critical operational risk vectors and structural revenue leaks:
 * **Platform Baseline:** The system exhibits a baseline **28.6% Churn Rate**, corresponding to a **71.4% Retention Rate**. The average user lifespan spans **1,451 days** with an Average Revenue Per User (ARPU) of **Rs 18.8**.
 * **The Contract Friction Point:** A severe structural disparity exists between contract structures. Subscribers on **monthly contracts churned at an alarming 55.6%**, which represents a **6.7x multiplier** compared to the highly stable **8.3% annual contract cohort**.
 * **Quantified Financial Loss:** Financial leaks account for an **18% total revenue drop**. Out of an evaluated total revenue of $395, churn events directly caused **$73.94/month in MRR leakage** and a massive **$2,047 in Customer Lifetime Value (CLTV) erosion**.
 * **Spikes & Geographic Anomalies:** Attrition patterns were not uniform; a major churn anomaly peaked during **September 2024**, with the state of **Karnataka** isolated as the most severely impacted region. Volume analysis indicates that the bulk of these exits originated within the **Basic subscription plan** tier.
 * **Support Intelligence Link:** Support cross-correlations demonstrate that escalated complaints and poor CSAT metrics are heavily concentrated within churned cohorts, proving a direct line from unresolved support friction to financial churn.
## 🎯 Action Items & Growth Roadmap
Based on empirical findings detailed in **Data Analytics Project -Churn Analysis Report.pdf**, the platform growth and operations teams should execute the following strategic actions:
 1. **Conduct Regional Root-Cause Analysis:** Launch an immediate operational audit into the September 2024 Karnataka anomaly. Cross-verify localized application downtime, platform bugs, targeted competitor promotions, or regional price changes during that specific month.
 2. **Deploy Competitor Defenses:** Qualitative cancellation comments flag subscriber poaching. Review competitor content catalogs, pricing changes, and localized user acquisition offers to establish defensive parity.
 3. **Automate a Prioritized Intervention Matrix:** Isolate active users flagged with "Medium" and "High" churn scores. Sort this cohort by their individual Customer Lifetime Value (CLTV) to establish a high-yield priority target list. Deploy automated win-back and resolution protocols via integrated email, SMS, and direct support calls to resolve open complaints.
 4. **Execute Contract-Migration Frameworks:** Because monthly structures suffer a 6.7x higher failure rate than annual structures, marketing efforts should pivot away from low-tier monthly customer acquisition. Shift budget toward migrating existing monthly users into long-term annual contracts via targeted loyalty discounts, stabilizing platform MRR and extending average customer lifetime value.
*Note: This repository represents an end-to-end implementation of the analytics roadmap designed and developed by Senior Data Analyst Rishabh Mishra. All core data architectures, metrics formulas, and business recommendations correspond directly to the source reference master file: **Data Analytics Project -Churn Analysis Report.pdf**.*
