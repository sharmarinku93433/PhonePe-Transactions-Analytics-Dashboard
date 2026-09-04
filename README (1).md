# PhonePe Transactions Analytics Dashboard

![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-yellow)
![Excel](https://img.shields.io/badge/Data-Microsoft%20Excel-green)
![Power Query](https://img.shields.io/badge/ETL-Power%20Query-blue)
![DAX](https://img.shields.io/badge/Analytics-DAX-purple)
![Status](https://img.shields.io/badge/Status-Completed-success)

## 📌 Project Overview

The **PhonePe Transactions Analytics Dashboard** is a multi-page **Power BI Business Intelligence project** designed to analyze digital payment transactions across four major service categories: **Insurance, Loans, Money Transfer, and Recharge & Bills**.

The project converts a large transactional dataset into an interactive five-page dashboard containing a platform-wide Overview and dedicated analytical pages for each service.

The dashboard helps users understand **transaction volume, transaction value, payment success/failure patterns, failure reasons, service-wise contribution, category-level performance, and monthly transaction trends**.

> **Data Note:** The dataset used in this project is synthetically generated for educational and portfolio purposes and does not represent real PhonePe customer or transaction data.

---

## 🎯 Project Objectives

- Build a platform-wide transaction overview.
- Analyze service-wise transaction value and volume.
- Monitor successful and failed transactions.
- Identify major payment failure reasons.
- Analyze monthly transaction amount trends.
- Provide dedicated analysis for Insurance, Loans, Money Transfer, and Recharge & Bills.
- Create a consistent, interactive and easy-to-use Power BI dashboard.
- Demonstrate multi-table data modeling, Power Query and DAX skills.

---

## 🛠️ Tools & Technologies

| Tool / Technology | Purpose |
|---|---|
| **Microsoft Excel** | Source dataset and initial data validation |
| **Power Query** | Data cleaning, transformation and validation |
| **Power BI Desktop** | Dashboard development and visualization |
| **DAX** | Calculated measures and KPI calculations |
| **Power BI Slicers** | Date filtering and interaction |
| **Power BI Page Navigation** | Navigation between dashboard pages |

---

## 📊 Dataset Overview

The project uses a six-sheet Excel workbook containing **300,000 transactions** and **107,658 registered users**.

| Sheet | Rows | Purpose |
|---|---:|---|
| `All_Users` | 107,658 | User master information |
| `All_Transactions` | 300,000 | Master transaction log |
| `Insurance` | 50,000 | Insurance transactions |
| `Loans` | 50,000 | Loan-related transactions |
| `Money_Transfer` | 150,000 | Peer-to-peer money transfers |
| `Recharge_Bills` | 50,000 | Recharge and bill payments |

The dataset covers the **2024 calendar year** and contains transaction amount, service, payment status, failure reason, date and service-specific category fields.

---

# 📸 Dashboard Screenshots

The screenshots below should be placed in the repository's `screenshots/` folder. They are intended to show the actual dashboard pages documented in the project report.

### 1. Overview Dashboard

![PhonePe Overview Dashboard](screenshots/01_overview_dashboard.png)

The Overview page provides a platform-wide summary including total transaction amount, successful transactions, total transactions, failed transactions, service-wise amount comparison, failure reasons and monthly trends.

### 2. Insurance Dashboard

![PhonePe Insurance Dashboard](screenshots/02_insurance_dashboard.png)

The Insurance page analyzes payment status, failure reasons, insurance categories and monthly transaction trends.

### 3. Loans Dashboard

![PhonePe Loans Dashboard](screenshots/03_loans_dashboard.png)

The Loans page focuses on loan transaction value, payment success rate, failure reasons, loan categories and monthly trends.

### 4. Money Transfer Dashboard

![PhonePe Money Transfer Dashboard](screenshots/04_money_transfer_dashboard.png)

The Money Transfer page analyzes transaction volume, transfer types, payment status, failure reasons and monthly transaction trends.

### 5. Recharge & Bills Dashboard

![PhonePe Recharge & Bills Dashboard](screenshots/05_recharge_bills_dashboard.png)

The Recharge & Bills page analyzes utility payment categories, payment success rate, failure reasons and monthly transaction trends.

> **Screenshot source:** These images should be exported directly from the Power BI dashboard/report so that GitHub displays the exact dashboard visuals.

---

## 📈 Key Dashboard Metrics

The complete platform-level dashboard reports:

| Metric | Value |
|---|---:|
| **Total Transactions** | 300,000 |
| **Successful Transactions** | 287,993 |
| **Failed Transactions** | 12,007 |
| **Total Transaction Amount** | ₹3,333M |
| **Overall Success Rate** | ~96% |
| **Registered Users** | 107,658 |

---

## 🏆 Service-wise Summary

| Service | Transactions | Total Amount | Success Rate |
|---|---:|---:|---:|
| **Insurance** | 50,000 | ₹512.92M | 95.75% |
| **Loans** | 50,000 | ₹2,532.51M | 95.95% |
| **Money Transfer** | 150,000 | ₹378M | 95.98% |
| **Recharge & Bills** | 50,000 | ₹50.69M | 96.16% |

### Important Observations

- **Loans** contributes the highest transaction value at **₹2,532.51M**.
- **Money Transfer** has the highest transaction volume with **150,000 transactions**.
- **Recharge & Bills** has the highest payment success rate at **96.16%**.
- Insurance contributes **₹512.92M** with a **95.75%** success rate.
- Money Transfer contributes **₹378M** with a **95.98%** success rate.

---

## ❌ Payment Failure Analysis

There are **12,007 failed transactions** across the platform.

Major failure reasons include:

| Failure Reason | Count | Share |
|---|---:|---:|
| **Server Error** | 4,053 | 33.76% |
| **Wrong PIN** | 3,315 | 27.61% |
| **Insufficient Amount** | 3,304 | 27.53% |
| **Wrong Info** | 700 | 5.83% |
| **Bank Denied** | 635 | 5.29% |

The analysis shows that **server-related failures and user-input-related failures** are the major contributors to failed transactions.

---

## 🔄 Project Workflow

```text
Six-Sheet Excel Dataset
          ↓
Data Inspection & Validation
          ↓
Power Query
          ↓
Data Cleaning & Transformation
          ↓
Power BI Data Model
          ↓
DAX Measures
          ↓
Dashboard Visualizations
          ↓
Interactive Filters & Navigation
          ↓
Testing & Validation
          ↓
Final Business Insights
```

---

## 🧹 Data Preparation

The following preparation activities were performed:

1. Imported all six Excel sheets into Power BI.
2. Checked row counts and transaction totals.
3. Validated service-specific sheets against the master transaction table.
4. Verified date fields for correct date-type handling.
5. Standardized category labels.
6. Reviewed payment status and failure-reason values.
7. Prepared the model for month-wise and service-wise analysis.
8. Created DAX measures for dashboard KPIs.

---

## 🧮 DAX Measures

The project uses DAX for dynamic KPI calculations.

### Total Amount

```DAX
Total Amount = SUM(All_Transactions[Amount])
```

### Total Transactions

```DAX
Total Transactions = COUNTROWS(All_Transactions)
```

### Successful Transactions

```DAX
Successful Txns =
CALCULATE(
    [Total Transactions],
    All_Transactions[Payment_Status] = "Successful"
)
```

### Failed Transactions

```DAX
Failed Txns =
[Total Transactions] - [Successful Txns]
```

### Success Rate

```DAX
Success Rate =
DIVIDE(
    [Successful Txns],
    [Total Transactions]
)
```

### Service-wise Amount

```DAX
Service Amount =
SUM(All_Transactions[Amount])
```

These measures respond to the active filter context, allowing dashboard values to change according to the selected date range and service.

---

## 🎛️ Dashboard Interactivity

The dashboard contains:

- **Date Range slicer**
- **Service navigation sidebar**
- **Overview page**
- **Insurance page**
- **Loans page**
- **Money Transfer page**
- **Recharge & Bills page**

Users can select a custom date range and navigate between service pages while the relevant visuals recalculate according to the active filter.

---

## 💡 Key Analytical Insights

### Loans — Highest Value

Loans generate the largest transaction value with **₹2,532.51M**, despite having 50,000 transactions.

### Money Transfer — Highest Volume

Money Transfer contains **150,000 transactions**, three times the transaction count of each other service.

### Recharge & Bills — Highest Reliability

Recharge & Bills records the highest success rate at **96.16%**.

### Failure Reasons

Server errors, Wrong PIN and Insufficient Amount are the dominant failure categories.

### Monthly Trends

The dashboard provides month-wise transaction amount analysis to identify peaks, dips and potential seasonal patterns.

---

## 🧪 Testing & Validation

The dashboard was tested against the source Excel data.

Validation included:

- Total transaction count
- Service-wise transaction counts
- Service-wise transaction amounts
- Successful vs failed transaction counts
- Payment status percentages
- Failure-reason percentages
- Date-range filtering
- Single-month filtering
- Navigation between pages
- KPI recalculation under filters

All documented functional test cases passed.

The source data contains **300,000 transactions**, including **287,993 successful** and **12,007 failed** transactions, and the dashboard was validated against these totals.

---

## 🎨 UI/UX Design

The dashboard follows a consistent multi-page design.

Key design decisions include:

- PhonePe-inspired purple visual theme
- Consistent sidebar navigation
- Consistent KPI placement
- Clear chart hierarchy
- Date Range filter at the top
- Consistent layout across service pages
- Percentage and absolute values shown where appropriate
- Simple navigation for non-technical users

This makes the dashboard easier to learn and navigate across all five pages.

---

## ⚠️ Challenges & Solutions

### Challenge 1 — Multiple Related Sheets

**Challenge:** Six related sheets needed to be validated and modeled correctly.

**Solution:** Service-specific totals were cross-checked against the master transaction table before dashboard development.

### Challenge 2 — Large Dataset

**Challenge:** The project contains 300,000 transaction records.

**Solution:** Power BI's in-memory data engine was used to handle the dataset efficiently.

### Challenge 3 — Consistent Multi-Page Design

**Challenge:** Five pages could easily become visually inconsistent.

**Solution:** A common page template was designed and reused across all service pages.

### Challenge 4 — Payment Status Inconsistency

**Challenge:** Some failure reasons were stored directly in payment-status values.

**Solution:** Non-successful values were standardized as Failed for payment-status analysis while retaining the original reason for failure analysis.

---

## 📚 Learning Outcomes

This project strengthened practical skills in:

- Power BI
- Microsoft Excel
- Power Query
- DAX
- Data Cleaning
- Data Transformation
- Data Modeling
- KPI Development
- Data Visualization
- Dashboard Design
- Interactive Filtering
- Data Validation
- Business Intelligence
- Analytical Storytelling

---

## ⚠️ Limitations

- Dataset is synthetically generated.
- Analysis covers the services included in the provided dataset.
- User-level demographic analysis is not currently included in the dashboard.
- Geographic analysis is not included.
- Real-time/live transaction connectivity is not implemented.
- Year-over-year analysis is limited because the dataset currently covers 2024.

---

## 🚀 Future Scope

Future versions can include:

- User demographic analysis
- Age-wise transaction patterns
- Geographic analysis
- Year-over-year comparison
- Anomaly detection
- Automated alerts for high failure rates
- Real-time data connectivity
- Power BI Service deployment
- Role-based dashboard access
- Additional service categories

---

## 📁 Repository Structure

```text
PhonePe-Transactions-Analytics/
│
├── data/
│   └── Phonepe-Final-Dataset.xlsx
│
├── dashboard/
│   └── Phonepe_Dashboard.pdf
│
├── powerbi/
│   └── Phonepe_Dashboard.pbix
│
├── report/
│   └── PhonePe_Project_Report.pdf
│
├── screenshots/
│   ├── 01_overview_dashboard.png
│   ├── 02_insurance_dashboard.png
│   ├── 03_loans_dashboard.png
│   ├── 04_money_transfer_dashboard.png
│   └── 05_recharge_bills_dashboard.png
│
└── README.md
```

---

## ▶️ How to Use

1. Install **Power BI Desktop**.
2. Open `Phonepe_Dashboard.pbix`.
3. Allow the report to load.
4. Start from the **Overview** page.
5. Use the Date Range slicer to select a period.
6. Use the sidebar to navigate between services.
7. Review KPIs, payment status, failure reasons and monthly trends.
8. Use the source Excel file for detailed data verification.

---

## 📄 Project Report

The complete project report contains:

- Executive Summary
- Literature Review
- Requirement Analysis
- Introduction
- Technology Stack
- Dataset Description
- System Design & Data Flow
- Features & Functionality
- UI/UX Design
- Implementation Details
- Testing & Validation
- Service-wise Comparative Analysis
- User Manual
- Challenges & Solutions
- Conclusion & Future Scope
- Dataset Summary
- DAX Measures Reference
- Glossary
- References

---

## 🔐 Data Privacy & Usage

This project uses a **synthetically generated dataset** created for educational and portfolio purposes. It does not represent real PhonePe users or real PhonePe transaction records.

The project is intended for:

- Academic submission
- Portfolio demonstration
- GitHub projects
- Data Analyst interview discussion
- Power BI learning and demonstration

---

## 👨‍💻 Author

**Rinku Kumar Sharma**

**Skills:**  
`Power BI` · `Excel` · `Power Query` · `DAX` · `Data Analysis` · `Data Visualization` · `Business Intelligence`

---

## ⭐ Project Summary

The **PhonePe Transactions Analytics Dashboard** demonstrates an end-to-end Business Intelligence workflow using a realistically structured 300,000-row transactional dataset.

The project combines **Excel, Power Query, Power BI and DAX** to transform raw transaction data into a professional five-page interactive dashboard covering platform performance, service-wise analysis, payment failures and monthly trends.

It demonstrates practical skills that are directly relevant to **Data Analyst and Business Intelligence roles**.
