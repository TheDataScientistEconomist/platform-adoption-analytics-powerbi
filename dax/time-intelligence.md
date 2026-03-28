# Time Intelligence Notes

This project uses time analysis carefully because not all metrics should be treated the same way.

## Appropriate for Time Intelligence
These measures are flow-based and work well with monthly, quarterly, and YTD logic:
- total transactions
- transaction trends
- participation trends

## Not Appropriate for Standard Time Windows
These are stock-based cumulative measures:
- cumulative active partners
- cumulative platform users
- adoption opportunity

For these measures, the selected date should be interpreted as an "as of" point rather than a monthly flow.

## Example: Transactions in Last 12 Months

```DAX
Transactions Last 12 Months =
CALCULATE(
    [Total Transactions],
    DATESINPERIOD(
        'Date Table'[Date],
        MAX('Date Table'[Date]),
        -12,
        MONTH
    )
)
```