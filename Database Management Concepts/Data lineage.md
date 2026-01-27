**Data lineage is the end-to-end traceability of data as it moves from source systems through ingestion, transformation, storage, and consumption layers. It records where data originates, how it is transformed, and where it is ultimately used.**

## What Data lineage includes
- Source system where data is created
- Ingestion pipeline and ETL processes
- Transformation logic and business rules
- Storage layers such as data lakes and warehouses
- Downstream consumers such as dashboards, reports, and machine learning models
## Why it matters
- Builds trust in enterprise data
- Enables fast root-cause analysis of data issue
- Supports regulatory compliance and audit requirements
- Assesses downstream impact before pipeline change
- Strengthens data governance
## How it is implemented
- Capturing metadata during ETL execution
- Integrating lineage with data catalogs
- Using governance tools to visualize data flow
- Automating lineage tracking within orchestration frameworks

## **Simple example**

If a finance dashboard displays revenue incorrectly, data lineage allows teams to trace the metric back through transformation jobs to the original transaction system, quickly identify where the issue occurred, and fix it.


## Types of Data Lineage

1. Table-Level Data Lineage
2. Column-Level Data Lineage