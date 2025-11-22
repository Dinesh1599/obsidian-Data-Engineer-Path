#AccountUsageSchema
**A global, account-wide view of metadata.**

Think of it as Snowflake’s **log history + monitoring database** that Snowflake maintains for you.

 **Location:**  
SNOWFLAKE.ACCOUNT_USAGE.<view>

 **What it contains:**  
Historical metadata for **the entire account**, including:
- Query history
    
- Login history
    
- Warehouse usage
    
- Storage usage
    
- Table & view metadata
    
- Pipe & task history
    
- Stream history
    
- Billing/credit usage
    
- Object dependencies
    
 **Retention:**  
**365 days** (1 year)

 **Purpose:**  
Best for **auditing**, **governance**, **billing**, **usage reporting**, and **monitoring**.

 **Access:** 
Only roles with **MONITOR USAGE** or ACCOUNTADMIN privileges.

 **Latency:** 
There is a latency of ~2 hours for the view so get updated


# **INFORMATION_SCHEMA**

## **INFORMATION_SCHEMA**

Metadata within a specific database, with some account-level table functions.

Every database has its own:

`<DATABASE>.INFORMATION_SCHEMA.<view_or_function>`

---

## **Scope**

- The **views** contain metadata **only for that database** (not the entire account).
    
- The **table functions** can return some **short-term historical and usage data** (7–14 days), but NOT long-term history.
    

---

## **What it contains**

### **1. Metadata Views (real-time, NOT historical)**

- Tables
    
- Columns
    
- Views
    
- Procedures
    
- Functions
    
- Constraints
    
- Privileges
    
- Stage definitions
    
- Object references
    

These views reflect **only the current state** of objects.

### **2. Table Functions (short-term historical/usage)**

Examples:

- `QUERY_HISTORY()`
    
- `LOGIN_HISTORY()`
    
- `USAGE_HISTORY()`
    
- `DATA_TRANSFER_HISTORY()`
    
- `LOAD_HISTORY()`
    
- `PIPE_USAGE_HISTORY()`
    

These return **historical usage data**, but with **limited retention** (e.g., 7 days, 14 days) — not 365 days.

---

## **Retention**

- **Metadata views** → no history (real-time only)
    
- **Table functions** → short retention (varies per function)
    
- Long-term history is **NOT** in INFORMATION_SCHEMA — it is in `SNOWFLAKE.ACCOUNT_USAGE`.
    

---

## **Purpose**

- Real-time schema introspection
    
- Listing tables, columns, privileges, constraints, routines
    
- Lightweight modeling and validation
    
- Basic short-term usage history via table functions
    

---

## **Access**

Any role with:

- **USAGE on the database**
    
- **USAGE on the schema**


|Feature|ACCOUNT_USAGE|INFORMATION_SCHEMA|
|---|---|---|
|Scope|Entire account|Single database|
|Provider|Snowflake-managed|Standard SQL metadata|
|Historical data|Yes (1 year)|No|
|Performance impact|Slower (large views)|Fast|
|Access required|MONITOR USAGE|USAGE on DB/Schema|
|Typical use|Auditing, billing, security|Schema design, column metadata|