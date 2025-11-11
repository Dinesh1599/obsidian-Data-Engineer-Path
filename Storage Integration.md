1. Stores access information to an external cloud storage
2. Steps:
	1. Create Snowflake object
	2. Grant permission in Cloud Provider
	3. Assign role in Cloud provider
	4. Use it in a stage


3. Get the url of the container of the cloud storage.
4. Query for creating a Storage integration:
	```sql
	CREATE OR REPLACE STORAGE INTEGRATION <integration_name>
		TYPE = EXTERNAL_STORAGE
		STORAGE_PROVIDER = AZURE
		ENABLED = TRUE
		AZURE_TENANT_ID = <azure_tenant_id>
		STORAGE_ALLOWED_LOCATIONS = ('<container_url>') //can have multiple url
	```  

5. Once the storage integration is created, we will receive an AZURE_CONSENT_URL when running the query ``` DESC STORAGE INTEGRATION <integration_name>```

![[Pasted image 20251110195226.png]]

6. paste the url and and grant access
7. Assign a role:
	1. go to the IAM option in the blob container
	2. select add role assignment and select Storage blob data contributor
	3. select members and choose the snowflake application. 
		1. p.s. of you cannot remember the enterprise application name, go to Enterprise application. you'll find the name there.