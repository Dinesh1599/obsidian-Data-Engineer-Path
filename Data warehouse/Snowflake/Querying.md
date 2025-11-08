1. To create a table:
	1. CREATE TABLE "database"."schema"."table"
2. LIST Command - [[Snowflake Stages]] 
	1. List all all file and additional properties
		1. LIST @STAGE_NAME; - External Stage / Internal Named Stages
		2. LIST @~ User Stages
		3. LIST @%TABLE_STAGE_NAME : table Stage
3. [[COPY INTO]]
4. [[INSERT]]