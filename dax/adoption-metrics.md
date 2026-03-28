# Adoption Metrics

## Adoption Rate

**Purpose:**  
Shows platform users as a percentage of active partners.

```DAX
Adoption Rate =
DIVIDE([Cumulative Platform Users], [Cumulative Active Partners], 0)
```

---

## Adoption Opportunity

**Purpose:**  
Measures the number of active partners not yet using the platform.

```DAX
Adoption Opportunity =
[Cumulative Active Partners] - [Cumulative Platform Users]
```

---

## Participating User Rate

**Purpose:**  
Measures the share of platform users who are actively transacting.

```DAX
Participating User Rate =
DIVIDE(
    [Distinct Active Partners with Activity],
    [Cumulative Platform Users],
    0
)
```

**Notes:**  
This is useful when the platform has registered users but only a subset actively engages in transactions.