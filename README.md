## Subscription & Churn Analytics Project

---

## Task 1 – Data Cleaning and Preparation

---

### 1. Project

**Subscription and Churn Analytics** is a data preparation project focused on cleaning and standardizing SaaS customer, subscription, usage, churn, and support data for further analysis and dashboard development.

This project was completed as **Task 1 during my internship at SWYNEX Technologies**.

---

### 2. Objective

The main objective was to prepare reliable and analysis-ready data by identifying data quality issues, handling missing values, correcting data types, removing duplicates, standardizing categorical fields, and validating the cleaned tables.

---

### 3. Tables Used

The project uses **5 tables**:

1. **Accounts** – Customer/account information
2. **Churn Events** – Customer churn events and reasons
3. **Feature Usage** – Product feature usage and errors
4. **Subscriptions** – Subscription, plan and revenue information
5. **Support Tickets** – Customer support and satisfaction information

---

### 4. Data Quality Issues Identified

The initial data inspection identified the following issues:

**1. Missing Values**

* Churn Events contained missing `feedback_text` values.
* Subscriptions contained many missing `end_date` values.
* Support Tickets contained missing `satisfaction_score` values.

**2. Incorrect / Inconsistent Data Types**

* Date fields required conversion to proper datetime format.
* Numeric fields required numeric conversion.
* Boolean fields required standardization.

**3. Duplicate Records**

* Duplicate records were checked and removed using unique identifiers such as `churn_event_id` and `ticket_id`.

**4. Inconsistent Categorical Values**

* Text fields such as `reason_code` and `priority` contained inconsistent formatting.
* Values were standardized using trimming and lowercase conversion.

**5. Invalid / Inconsistent Values**

* Invalid support ticket timestamps were identified.
* Negative resolution and response times were removed.
* Churn records with conflicting upgrade and downgrade flags were filtered.

---

### 5. Cleaning Steps

The following data-cleaning process was performed using Python:

* Loaded all 5 tables using Pandas.
* Inspected shape, columns, data types and missing values.
* Removed unnecessary spaces from column names and text fields.
* Converted date/time columns using `pd.to_datetime()`.
* Converted numeric columns using `pd.to_numeric()`.
* Standardized Boolean fields into `True` / `False`.
* Handled missing values according to the field requirements.
* Removed duplicate records using unique IDs.
* Standardized categorical values such as priority and reason codes.
* Corrected invalid date relationships.
* Removed negative resolution and response-time values.
* Applied validation using `info()`, `describe()` and duplicate checks.
* Exported the cleaned tables as CSV files.

---

### 6. Initial Data

| Table           | Initial Records | Columns |
| --------------- | --------------: | ------: |
| Accounts        |             500 |      10 |
| Churn Events    |             600 |       9 |
| Feature Usage   |          25,000 |       8 |
| Subscriptions   |           5,000 |      14 |
| Support Tickets |           2,000 |       9 |

Examples of initial missing values:

* **Churn Events:** 148 missing `feedback_text`
* **Subscriptions:** 4,514 missing `end_date`
* **Support Tickets:** 825 missing `satisfaction_score`

---

### 7. Final Dataset

After cleaning, the processed tables were exported as separate CSV files:

```text
accounts_clean1.csv
churn_events_clean1.csv
feature_usage_clean1.csv
subscriptions_clean1.csv
support_tickets_clean1.csv
```

For example, the **Churn Events** table was reduced from 600 to **592 valid records** after duplicate/conflicting-record filtering, with all 9 columns populated and correctly typed.

The cleaned tables are now suitable for further **SQL analysis, data modeling and Power BI dashboard development**.

---

### 8. Files

```text
SaaS-Subscription-and-Churn-Analytics/
│
├── data/
│   ├── accounts_clean1.csv
│   ├── churn_events_clean1.csv
│   ├── feature_usage_clean1.csv
│   ├── subscriptions_clean1.csv
│   └── support_tickets_clean1.csv
│
├── python_notebook.ipynb
│
└── README.md
```

---

### 9. Tools Used

* **Python**
* **Pandas**
* **NumPy**
* **Jupyter Notebook**
* **CSV**

---

### 10. Conclusion

This task established a clean and consistent foundation for the SaaS analytics project. The five tables were inspected, cleaned, validated and exported into analysis-ready CSV files.

The cleaned data can now be used for **SQL-based analysis and Power BI dashboard development**, helping generate reliable customer, subscription, churn, product usage and support insights.
