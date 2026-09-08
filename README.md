# 📊 Loan Default & Financial Risk Analytics Dashboard (Power BI)

## 📌 Project Purpose
This Power BI dashboard provides an end-to-end exploratory and diagnostic analysis of consumer credit risk, loan volume, and default behavior. Built for credit analysts and risk underwriters, it bridges applicant demographics, employment data, and credit ratings to identify default drivers, track Year-over-Year (YoY) risk fluctuations, and support data-driven lending policies.

---

## 🛠️ Step-by-Step Implementation Workflow
1. **Data Ingestion & Cleaning (Power Query):**
   - Cleaned raw loan data, managed null values, and standardized categorical schemas (employment status, marital status, education).
   - Generated calculated groups: Age brackets (`Adults`, `Middle Age Adults`, `Senior Adults`, `Teen`) and Credit Score Bins (`High`, `Medium`, `Low`, `Very Low`).
2. **Data Modeling & DAX Architecture:**
   - Established dedicated measure tables (`Measures Table 1, 2, 3`) to separate business logic from source tables.
   - Authored DAX measures for core KPIs:
     - `Default Rate (%)` = $\frac{\text{Total Defaults}}{\text{Total Loans}} \times 100$
     - `YOY Loan Amount Change` and `YOY Default Loan Change` using time-intelligence functions (`SAMEPERIODLASTYEAR`, `DIVIDE`).
     - Dynamic segmentation of total loan distributions and median values across multi-tiered risk categories.
3. **UI/UX & Visual Layout:**
   - Applied a consistent, modern executive color palette with custom-styled KPI visual containers.
   - Deployed advanced chart types (Sankey diagrams, Decomposition Trees, Area and Stepped Area charts) to display both micro-level trends and macro risk factors.

---

## 📈 Visuals & Dashboard Breakdown

### Page 1: Loan Default Overview
* **Loan Amount By Purpose (Stepped Area Chart):** Compares total capital exposure across loan purposes, highlighting high-exposure products like Home and Business loans.
* **Average Income By Employment Type (Area Chart):** Assesses borrower earning capability across Full-time, Self-employed, Part-time, and Unemployed segments.
* **Default Rate (%) By Employment Type (Step Chart):** Highlights credit vulnerabilities, identifying which employment categories generate higher default probabilities.
* **Average Loan Amount By Age Group (Smooth Line Chart):** Evaluates borrowing size lifecycle patterns across Age segments (Adults down to Teens).
* **Default Rate (%) By Year (2013–2018 Line/Area Chart):** Visualizes the longitudinal default cycle, emphasizing risk peaks and recovery trends over a 5-year period.

### Page 2: Applicant Demographics & Financial Profile
* **Median Loan Amount By Credit Score (Area Chart):** Tracks relationship between credit risk bands and borrowed principal amounts.
* **Avg Loan Amnt (High Credit) by Age Groups & Marital Status (Donut Chart):** Examines high-tier credit utilization broken down by marital status (Single, Married, Divorced) within age groups.
* **Total Loan (Adults) By Credit Score Bins (Area Chart):** Maps portfolio volume across High, Medium, Very Low, and Low credit tiers specifically for the primary adult segment.
* **Loan Distribution by Mortgage & Dependents (Clustered Column Chart):** Assesses debt exposure factoring in existing liabilities (mortgages) and dependent obligations.
* **No of Loans By Education Type (Area/Ribbon Chart):** Analyzes portfolio volume across education levels (Bachelor's, High School, Master's, PhD).

### Page 3: Financial Risk Metrics
* **YOY Loan Amount Change by Year (Area Chart):** Measures annual growth or contraction of total loan originations.
* **YOY Default Loan Change by Year (Area Chart):** Tracks annual rate of change in defaulted loans to identify deteriorating credit vintages early.
* **YTD Loan Amount by Credit Score Bins & Marital Status (Sankey Diagram):** Tracks loan capital flow across credit tiers into applicant marital demographics.
* **Loan Exposure Breakdown (Decomposition Tree):** Enables interactive ad-hoc root-cause analysis by drilling into total loan volume ($32.58B) across Income Brackets (High, Medium, Low) and Employment Types.

---

## 💡 Key Business Insights
- Borrowers with lower-tier credit and non-salaried employment drive the highest default concentrations, despite lower median loan tickets.
- Portfolio exposure is heavily weighted toward high-income brackets ($21.73B of the $32.58B total balance), balancing aggregate risk.
- Year-over-year default volatility spiked sharply in 2015 and 2018, requiring dynamic lending criteria adjustments during economic contraction cycles.
