
## OLTP (Online  Transactional Processing)
- Can Handle writes very easily
- Best to store data immediately
- [[Normalization]] modeling is considered the core here.
- Focused on handling large number of transactional data quickly for daily business operations!
- Maintains integrity and reliability and supports [[ACID Transaction]]
- **Basically anything that involves transactions**

## OLAP (Online Analytical Processing)
- Multi-dimensional processing done on high speed to process Big Data
- Good for tasks like data Mining, BI and analytics calculations. 
- Its mostly downstream and a read-only for Business Intelligence.


# OLAP vs OLTP

	Choosing when to use OLAP and OLTP depends on what you need

| **Feature**      | **OLTP**                  | **OLAP**                              |
| ---------------- | ------------------------- | ------------------------------------- |
| Primary purpose  | Run operations            | Analyze business                      |
| Typical users    | Applications, customers   | Analysts, data scientists, executives |
| Workload type    | Many small transactions   | Few large complex queries             |
| Data freshness   | Real-time current state   | Historical + aggregated               |
| Schema design    | Highly normalized (3NF)   | Denormalized (Star / Wide tables)     |
| Storage pattern  | Row-oriented              | Column-oriented                       |
| Read vs Write    | Write-heavy               | Read-heavy                            |
| Query complexity | Simple point queries      | Large joins + aggregations            |
| Data size        | GB–TB                     | TB–PB                                 |
| Examples         | PostgreSQL, MySQL, Oracle | Snowflake, BigQuery, Redshift         |

Usually, A typical pipeline generally converts data in OLTP model to OLAP model
```
App Database (OLTP)
     ↓ ETL / CDC
Data Warehouse (OLAP)
     ↓
Dashboards / ML / Reports
```
