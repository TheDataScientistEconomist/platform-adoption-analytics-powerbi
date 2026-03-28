# Core KPI Measures

## Total Transactions

**Purpose:**  
Counts total platform transactions in the selected context.

```DAX
Total Transactions =
SUM(fact_platform_activity[transaction_count])
```

## Distinct Active Users

**Purpose:**  
Counts distinct users active on the platform.

```DAX
Distinct Active Users =
DISTINCTCOUNT(fact_platform_activity[user_id])
```

## Distinct Active Partners with Activity

**Purpose:**  
Counts distinct partners generating platform activity.

```DAX
Distinct Active Partners with Activity =
DISTINCTCOUNT(fact_platform_activity[partner_id])
```