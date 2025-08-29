
### **Step 1 – Data Ingestion & Staging**

- Define environment variables (Oracle DSN, user, password, data paths). - done
    
- Load raw CSV files (customers, accounts, transactions, merchants, devices, branches, geos) into Python (pandas). - done
    
- Apply basic cleaning (strip(), trim whitespace, lowercase, datatype checks).
    
- Create **staging tables** in Oracle (raw schema).
    
- Bulk-insert the cleaned CSV data into staging.
    
- Validate row counts vs source files.
    

---

### **Step 2 – Curated Warehouse (Relational Model)**

- Design **dimensional schema**:
    
    - Dimensions: `dim_customer`, `dim_account`, `dim_merchant`, `dim_branch`, `dim_geo`, `dim_device`.
        
    - Fact tables: `fact_txn`, `fact_login`.
        
- Apply surrogate keys, foreign key relationships, partitioning (e.g., by txn_date).
    
- Create **materialized views** for daily/weekly aggregates (txn amount, count, per branch/currency).
    
- Implement indexes and constraints.
    
- Run validation queries (compare fact counts against staging).
    

---

### **Step 3 – ETL/ELT Orchestration**

- Automate ingestion & loading with **Airflow DAGs / Python jobs**.
    
- Add data quality checks (nulls, duplicates, referential integrity).
    
- Schedule incremental loads (e.g., load yesterday’s transactions only).
    
- Implement error handling + logging (retry on failure, log success/failure).
    

---

### **Step 4 – Graph Database Integration**

- Load entities + relationships into **Neo4j**:
    
    - `(Customer)-[:OWNS]->(Account)`
        
    - `(Account)-[:TRANSACTED_WITH]->(Merchant)`
        
    - `(Customer)-[:LOGGED_IN_FROM]->(Device)`
        
    - `(Customer)-[:IN_COUNTRY]->(Geo)`
        
- Use **Neo4j APOC** procedures for bulk import.
    
- Validate edge counts vs fact tables.
    

---

### **Step 5 – Graph Data Science (GDS)**

- Run algorithms for fraud/risk detection:
    
    - **PageRank** → influential accounts/merchants.
        
    - **Community Detection (Louvain)** → fraud rings or colluding accounts.
        
    - **Link Prediction** → suspicious connections not yet observed.
        
    - **Embeddings** → cluster customers by behavioral similarity.
        
- Store outputs back into Oracle fact tables or Neo4j properties.
    

---

### **Step 6 – Generative AI / GraphRAG Layer**

- Build a **GraphRAG pipeline**:
    
    - Extract subgraphs relevant to a flagged transaction.
        
    - Feed context into an LLM prompt.
        
    - Generate **investigator narratives** explaining suspicious behavior.
        
- Package as a Python/Flask or Streamlit app.
    

---

### **Step 7 – Observability & Compliance**

- Implement monitoring (Airflow logs, Oracle/AWR, Neo4j metrics).
    
- Add **audit logs** for data lineage (staging → warehouse → graph).
    
- Apply basic **data masking** on PII fields (customer name, email, phone).
    
- Document compliance mapping (AML, KYC, SAR).
    

---

### **Step 8 – Final Delivery**

- Deliverables:
    
    - Oracle relational warehouse (curated schema + MVs).
        
    - Neo4j graph model with GDS outputs.
        
    - Automated ETL/ELT pipelines with Airflow.
        
    - Fraud detection dashboard (Oracle BI/Power BI or Neo4j Bloom).
        
    - GenAI narrative generator.
        
- Write **README.md** + architecture diagram + flowchart.


![[Pasted image 20250829111952.png]]