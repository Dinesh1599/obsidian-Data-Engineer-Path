
**TOPICS**
- [[ETL]]
- [[ETL Layers]]
- [[Incremental Loading]]
- 


ETL (Extract Transform Load)
- ETL is the pipeline that extracts data from operational OLTP systems, transforms it into clean structured formats, and loads it into OLAP systems for analytics and reporting.
- Extract
	- Pulls Data from source systems
		- Application databases
		- APIs
		- Logs
		- Files
		- Streaming platforms
	- Goal: Get Raw data from operational system
- Transform
	- Clean and reshape data
		- Fix Data types
		- Remove duplicates
		- Apply Business Logics
		- Join Datasets
		- Create aggregates
	- Goal: Make Data consistent and analytics ready
- Load
	- Show transformed data into
		- Data warehouses
		- Data Lakes
		- Analytics database
	- Goal: Make data available for queries and dashboards.