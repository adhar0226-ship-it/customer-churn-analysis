# Data Dictionary: Customer Churn Dataset

| Column Name | Data Type | Field Meaning | Allowed Values / Range | Quality Rules & Audit Notes |
| :--- | :--- | :--- | :--- | :--- |
| `CustomerID` | String | Synthetic unique identifier | `CUST-1001` to `CUST-1015` | Unique key. Never aggregate as a measure. No duplicates or nulls found. |
| `Gender` | String | Gender of the customer | `Female`, `Male` | Non-null categorical field. |
| `Age` | Integer | Age in years | 23 – 60 | No impossible or extreme values detected. |
| `TenureMonths` | Integer | Completed months since signup | 2 – 48 | No missing values or negative values. |
| `SubscriptionType` | String | Subscription tier | `Basic`, `Pro`, `Enterprise` | Clean categorical values. |
| `MonthlyCharges` | Float | Fictional monthly charge in INR | ₹49.99 – ₹149.99 | Numeric measure. Verified against `TotalCharges`. |
| `TotalCharges` | Float | Total cumulative charge in INR | ₹99.98 – ₹7199.52 | Equals `MonthlyCharges` × `TenureMonths` across all rows. |
| `ContractType` | String | Duration of contract | `Month-to-Month`, `One Year`, `Two Year` | Key driver for churn segmentation. |
| `SupportTickets` | Integer | Count of support tickets in past 90 days | 0 – 6 | Key indicator of customer friction. |
| `PaymentMethod` | String | Payment method on file | `Credit Card`, `Debit Card`, `UPI`, `Bank Transfer` | Non-null categorical field. |
| `Churn` | String | Whether customer churned in period | `Yes`, `No` | Binary target variable. |
