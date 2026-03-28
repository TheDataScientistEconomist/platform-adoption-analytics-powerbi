# Simplified Data Model

The model uses a star-schema approach with dimension and fact tables.

## Core Tables

### `dim_partner`
Contains partner-level attributes such as:
- partner_id
- active_date
- termination_date
- partner_maturity_group
- organizational grouping fields

### `fact_platform_activity`
Contains platform transaction/activity records such as:
- transaction_date
- partner_id
- user_id
- transaction_count
- transaction_type

### `date_table`
Standard date dimension used for slicing and time-based calculations.

## Modeling Notes

- `dim_partner` links to `fact_platform_activity` through partner identifiers
- `date_table` is related to activity date for transaction-based analysis
- cumulative partner counts are driven from partner effective dates
- cumulative user counts are derived from distinct partners/users with platform activity