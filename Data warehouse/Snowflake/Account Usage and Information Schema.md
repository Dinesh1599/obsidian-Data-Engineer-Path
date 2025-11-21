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


# **INFORMATION_SCHEMA**

Metadata **within a specific database/schema**.

Every database has its own:

`<DATABASE>.INFORMATION_SCHEMA.<view>`

 **Scope:**  
Contains metadata **only for that one database** (not the entire account).

 **What it contains:**
- Tables
    
- Columns
    
- Views
    
- Procedures
    
- Functions
    
- Constraints
    
- Privileges
    
- Stage definitions
    
- Object references
    
 **Retention:**  
Not historical — **real-time** metadata.

 **Purpose:**  
Good for **data modeling**, **query building**, **schema introspection**, and **validations**.

 **Access:**  
Any role with **USAGE** on database + schema.


|Feature|ACCOUNT_USAGE|INFORMATION_SCHEMA|
|---|---|---|
|Scope|Entire account|Single database|
|Provider|Snowflake-managed|Standard SQL metadata|
|Historical data|Yes (1 year)|No|
|Performance impact|Slower (large views)|Fast|
|Access required|MONITOR USAGE|USAGE on DB/Schema|
|Typical use|Auditing, billing, security|Schema design, column metadata|