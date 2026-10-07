# 🏦 Indian Banking Transactions Analysis using Excel

An end-to-end data analytics project built in **Microsoft Excel** that turns 500 raw banking transaction records into business insights through data cleaning, feature engineering, PivotTables, KPIs, and an interactive dashboard with slicers.

---

## 📌 Table of Contents
- [Project Overview](#-project-overview)
- [Business Objectives](#-business-objectives)
- [Dataset](#-dataset)
- [Tools & Skills](#-tools--skills)
- [Project Workflow](#-project-workflow)
- [Step 1: Raw Data](#step-1--raw-data)
- [Step 2: Data Understanding](#step-2--data-understanding)
- [Step 3: Data Cleaning & Transformation](#step-3--data-cleaning--transformation)
- [Step 4: Pivot Analysis](#step-4--pivot-analysis)
- [Step 5: KPI Analysis](#step-5--kpi-analysis)
- [Step 6: Interactive Dashboard](#step-6--interactive-dashboard)
- [Key Insights](#-key-insights)
- [Business Recommendations](#-business-recommendations)
- [Limitations](#-limitations)
- [Project Structure](#-project-structure)
- [Author](#-author)

---

## 📖 Project Overview

Banks process a large volume of transactions every day, and storing this data is not enough. It must be analyzed to understand regional performance, payment behavior, transaction outcomes, and possible fraud patterns. This project follows a structured workflow from **raw data → cleaned data → pivot summaries → KPIs → executive dashboard**.

## 🎯 Business Objectives

- Analyze transaction trends across **regions, branches, and months**
- Identify **fraud-flagged transactions** and branch-level fraud patterns
- Compare **payment modes** (Debit Card, Credit Card, Cash, UPI, Net Banking)
- Track **transaction status** (Completed, Failed, Reversed, Pending)
- Build an **interactive Excel dashboard** with KPI cards and slicers for leadership

## 📊 Dataset

- **Source:** Indian Banking Domain dataset
- **Records:** 500 transactions | **Distinct customers:** 500
- **Period covered:** July 2023 – July 2025

| Field | Description |
|---|---|
| Transaction ID, Customer ID, Customer Name, Account Number | Identifiers |
| Region, City, Branch Name | Geographic hierarchy |
| Account Type | Current, Fixed Deposit, Recurring Deposit, Savings |
| Transaction Type | Cheque, Deposit, Online Transfer, Withdrawal |
| Transaction Amount, Balance After Txn | Numeric measures |
| Payment Mode | Debit Card, Credit Card, Cash, UPI, Net Banking |
| Transaction Date, Transaction Status | Date and outcome |
| Is Fraud | Yes / No fraud indicator |
| **Year-Month, Net Change, Fraud Flag** | *Derived fields created in this project* |

## 🛠 Tools & Skills

- **Tool:** Microsoft Excel
- **Skills:** Data cleaning, PivotTables, slicers, KPI design, charts (bar, line, donut), dashboard design, business storytelling

## 🔄 Project Workflow

| Step | Stage | Output |
|---|---|---|
| 1 | Data Understanding | Field meanings, data types, business purpose |
| 2 | Data Cleaning | Duplicate, missing-value, text and date checks |
| 3 | Transformation | Year-Month, Net Change, Fraud Flag |
| 4 | Pivot Analysis | 9 PivotTables + fraud-by-branch view |
| 5 | KPI Analysis | 10 management KPIs |
| 6 | Dashboard | 4 charts + KPI cards + 5 slicers |

**Workbook sheets:** `Raw_Data` · `Cleaned_Data` · `Data_Understanding` · `Pivot Analysis` · `KPI Analysis` · `Dashboard`

---

## Step 1 – Raw Data

The original transaction data is preserved untouched in the `Raw_Data` sheet so the cleaning process stays auditable.

<img width="1861" height="767" alt="raw data" src="https://github.com/user-attachments/assets/21a77fed-ac7f-4e0e-ad81-94d629db6108" />


## Step 2 – Data Understanding

Every column was reviewed for its data type, category (identifier, geographic, categorical, measure, time, flag, derived) and business purpose before any analysis began.

<img width="1880" height="795" alt="Data Understanding" src="https://github.com/user-attachments/assets/5455d50f-7476-4a90-8f0d-0ca28f583f85" />


## Step 3 – Data Cleaning & Transformation

The `Cleaned_Data` sheet contains the validated dataset in a formatted table.

- **Duplicate check** using Transaction ID
- **Missing-value check** on Amount, Date and Transaction Type
- **Text standardization** for Region, Branch Name and Transaction Type
- **Negative value and date validity** review
- Corrected one inconsistent Transaction Type value during validation

**Derived fields:**
- `Year-Month` – month label from Transaction Date (yyyy-mm) for trend analysis
- `Net Change` – Withdrawals as negative, other transaction types as positive
- `Fraud Flag` – numeric 1/0 version of Is Fraud

<img width="1872" height="776" alt="Cleaned Data" src="https://github.com/user-attachments/assets/de231adb-2e87-4754-bdf2-6c09be507bbf" />


## Step 4 – Pivot Analysis

PivotTables summarize the cleaned data across region, month, branch, transaction type, payment mode, status, fraud, account type, and city, plus a fraud-by-branch cross view.

<img width="1867" height="787" alt="Pivot Analysis" src="https://github.com/user-attachments/assets/1031c86f-5f1a-4528-8a68-3eea9b2f2b4f" />

## Step 5 – KPI Analysis

| KPI | Result |
|---|---|
| Total Transactions | 500 |
| Total Transaction Amount | ₹93,933,780.49 |
| Average Transaction Amount | ≈ ₹187,867.56 |
| Total Customers | 500 |
| Total Frauds | 13 |
| Fraud Rate | 2.60% |
| Completed / Failed / Reversed / Pending | 434 / 26 / 21 / 19 |

<img width="1865" height="787" alt="KPI Analysis" src="https://github.com/user-attachments/assets/22b4c422-ef6a-4d6e-bb99-d4c19c643c77" />

## Step 6 – Interactive Dashboard

A single-page executive dashboard with KPI cards, four charts, and slicers for **Transaction Status, Transaction Type, Is Fraud, Region, and Payment Mode**.

| Chart | Type | Purpose |
|---|---|---|
| Regional Transaction Volume | Bar | Compare activity across regions |
| Monthly Transaction Trend | Line | Show volume over time |
| Payment Mode Usage | Donut | Compare payment modes |
| Fraud Pattern by Branch | Stacked bar | Compare fraud flags across branches |

<img width="1167" height="692" alt="Dashboard" src="https://github.com/user-attachments/assets/169f6458-b85c-492d-ab5c-b7d5141c37fd" />

---

## 🔍 Key Insights

- **Regions:** North leads with 110 transactions, followed by West (101), Central (98), South (97) and East (94). The spread is modest, so no single region dominates.
- **Payment modes:** Debit Card is most used (128), then Credit Card (100), Cash (98), UPI (94) and Net Banking (80).
- **Transaction types:** Deposit (140) and Online Transfer (136) are the largest, followed by Withdrawal (116) and Cheque (108).
- **Account types:** Recurring Deposit has the highest count (137); Savings the lowest (117).
- **Outcomes:** 86.8% of transactions are completed; failed, reversed and pending together make up 66 records (13.2%) that need operational follow-up.
- **Fraud:** 13 of 500 transactions are flagged (2.60%). Bhopal Branch has the most flagged records (3); most other affected branches have 1.
- **Branch volume:** Chennai and Indore branches handle the most transactions (28 each); Mumbai has the fewest (12).

## 💡 Business Recommendations

1. **Monitor high-activity regions** and compare volume with staffing and service capacity.
2. **Track payment-mode adoption** over time, especially digital modes.
3. **Investigate failed and reversed transactions** by branch, payment mode, type and month.
4. **Strengthen fraud monitoring** by combining amount, branch, mode, type, date and account patterns.
5. **Refresh the dashboard regularly** with new data using the same validate → pivot → KPI workflow.

## ⚠️ Limitations

- A fraud flag is an **indicator**, not a confirmed investigation result.
- The analysis shows patterns, **not causal relationships**.
- The project brief mentions "Channel"; the dataset field is **Payment Mode**, which was used in the dashboard.

## 📁 Project Structure

```
├── Indian_Banking_Transaction_Analysis.xlsx        # Complete Excel workbook
├── Indian_Banking_Transaction_Analysis_DOC.docx    # Detailed project documentation
├── images/
│   ├── 01_raw_data.png
│   ├── 02_data_understanding.png
│   ├── 03_cleaned_data.png
│   ├── 04_pivot_analysis.png
│   ├── 05_kpi_analysis.png
│   └── 06_dashboard.png
└── README.md
```

> 💡 Download the `.xlsx` file and open it in Excel to explore the PivotTables and use the dashboard slicers.

## 👤 Author

**Abhinav Yadav**
Aspiring Data Analyst | Hyderabad, India


---

⭐ If you found this project useful, consider giving it a star!
