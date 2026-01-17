1. CREATE STAGE and then URL = "path"  (URL is the only difference between internal named stage)
2. Snowflake database object
3. Everyone with privileges can access it
4. Referred with '@STAGE_NAME'
5. ==Use STORAGE_INTEGRATION object for better security==


Ways to create Stages:

1. basic method
2. With [[File Formats]] (Best Practice)
	```sql
	CREATE OR REPLACE STAGE MANAGE_DB.external_stages.aws_stage
	URL= 's3://bucketsnowflakes3'
	FILE_FORMAT = FORMAT_NAME=MANAGE_DB.file_formats.my_file_format);
	```
3. stage + [[File Formats]] + [[Storage Integration]]
```sql
create or replace stage manage_db.public.stage_azure
    STORAGE_INTEGRATION = azure_integration
    URL = 'https://<your-container-url>'
    FILE_FORMAT = fileformat_azure;
```