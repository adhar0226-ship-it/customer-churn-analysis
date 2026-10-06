# Customer Churn Quality Audit & Executive Brief

## Executive Recommendation

* **Target Audience**: Subscription Retention & Customer Support Leadership Teams.
* **Core Decision**: Proactively contact and offer plan upgrade incentives to **Month-to-Month contract customers with $\ge 3$ support tickets** in the prior 90 days.
* **Supporting Metric**: This high-friction segment accounts for **100% of historical churn** (7 out of 7 churned accounts; 0% churn among annual contract holders).
* **Uncertainty**: Small sample size ($N=15$). High ticket counts correlate strongly with churn, but underlying causes (e.g., product bugs vs. pricing friction) require root-cause ticket review.
* **Next Measurement**: Monitor **30-day ticket resolution satisfaction (CSAT)** and **60-day Month-to-Month renewal rates** post-outreach.

---

## Data Profiling & Quality Audit

* **Completeness & Uniqueness**: 15 records audited; 0 missing values; 0 duplicate `CustomerID` entries.
* **Consistency Check**: `TotalCharges` equals `MonthlyCharges` $\times$ `TenureMonths` across all rows.
* **Summary Statistics**:
  * **Churned Customers ($n=7$)**: Avg tenure = 7.0 months, avg monthly charge = ₹58.56, avg support tickets = 4.29.
  * **Retained Customers ($n=8$)**: Avg tenure = 29.13 months, avg monthly charge = ₹107.49, avg support tickets = 1.00.

---

## Data Dictionary

| Column Name | Data Type | Description | Quality Notes |
| :--- | :--- | :--- | :--- |
| `CustomerID` | String | Unique synthetic identifier | 100% unique, non-null |
| `TenureMonths` | Integer | Active months since signup | Range: 2–48 |
| `MonthlyCharges` | Float | Monthly fee in INR | Range: ₹49.99–₹149.99 |
| `SupportTickets` | Integer | Tickets in past 90 days | Range: 0–6 |
| `ContractType` | String | Month-to-Month, One Year, Two Year | Categorical |
| `Churn` | String | Lost in observation period (Yes/No) | Binary target |
