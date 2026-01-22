
## Definition

**Nested data** refers to data that contains **hierarchical sub-structures inside a single record**, instead of flat rows and columns.

In simple terms:  
**Data within data.**

---

## Flat vs Nested Example

### Flat Data (Relational Style)

| user_id | name   | city    |
|--------|--------|---------|
| 101    | Dinesh | Chicago |

Each column contains a single atomic value.

---

## Why Nested Data Matters

Analytics engines and SQL-based warehouses work best with **flat tables**.

Therefore nested data is usually:

- **Flattened** for analytics
    
- **Normalized** into multiple tables
    
- Or stored as **semi-structured columns**

## Handling Nested Data in Modern Warehouses

| Platform      | Nested Support Type    |
| ------------- | ---------------------- |
| [[Snowflake]] | VARIANT                |
| BigQuery      | STRUCT / ARRAY         |
| Databricks    | StructType / ArrayType |
| PostgreSQL    | JSON / JSONB           |
### Nested Data (JSON Style)
```JSON
{
  "user_id": 101,
  "name": "Dinesh",
  "address": {
    "city": "Chicago",
    "state": "IL"
  },
  "orders": [
    {"order_id": 9001, "amount": 120},
    {"order_id": 9002, "amount": 75}
  ]
}
```

