
1. Loads data immediately when a file appears in the storage
2. According to defined [[COPY INTO]] statement
3. if data needs to be available for immediate analysis
4. uses serverless features! 

How this works (Azure):
1.  Event Notifications are setup anytime a file is loaded into an Azure Container
2.  The Notification is sent to a Queue Storage
3. Notification integration watches the queue storage for any notification and triggers the pipe and loads to the database.
![[Pasted image 20251110205458.png]]

Query for Creating a pipe:
```sql
CREATE PIPE <NAME>
	AUTO_INGEST = TURE | FALSE
	INTEGRATION = '<string>' --the notification integration
	COMMENT = '<string_literal>'
	as <copy_statement>
```

Methods:
1. Cloud Messages
	1. Use event notifcation (SQS Queue)
	2. Only External Stages
2. REST API
	1. Calls REST APIs
	2. Can be for both Internal and External Stages

Cost: 
	per-second/per-core granuality (no: of cores in a compute cluster)

Load time:
	Typically a min

File Size:
	Ideally 100MB - 250MB

Cuz of the metadata - Load history is remembered for 14days so that no duplicates are loaded in that time period.

Location:
	Stored in a Schema

Pause and Resume
```sql
ALTER PIPE
	SET PIPE_EXECUTION_PAUSED = TRUE
```


Bulk Loading Vs Snowpipe:
![[Pasted image 20251124171631.png]]

Snowpipe Data Loading Best Practices:
1. File size: 100 - 250mb
2. Organize dates by a path
3. Seperate VH for Load and Query
4. Pre-sort Data
5. Load once per minute