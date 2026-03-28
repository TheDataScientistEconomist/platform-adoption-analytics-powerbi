# Ranking and Concentration Measures

## Partner Transaction Rank

**Purpose:**  
Ranks partners based on transaction volume.

```DAX
Partner Transaction Rank =
RANKX(
    ALL(dim_partner[partner_id]),
    [Total Transactions],
    ,
    DESC,
    DENSE
)
```

---

## Top N Transactions

**Purpose:**  
Calculates transaction volume contributed by the top N partners.

```DAX
Top N Transactions =
VAR TopNValue = SELECTEDVALUE('Top N Parameter'[Value], 10)
RETURN
CALCULATE(
    [Total Transactions],
    TOPN(
        TopNValue,
        ALL(dim_partner[partner_id]),
        [Total Transactions],
        DESC
    )
)
```

---

## Top User Contribution %

**Purpose:**  
Measures the share of total transactions driven by top users.

```DAX
Top User Contribution % =
DIVIDE([Top N Transactions], [Total Transactions], 0)
```

**Notes:**  
Useful for understanding concentration risk and dependency on a small user base.