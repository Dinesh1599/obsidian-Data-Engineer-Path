    When data needs to be copied into a table
1. Upload the file into the internal stage
	1. Data is compressed into a .gz file
	2. Automatically encrypted in 128-bit or 256-bit
2. To load:
	1. Use PUT command in snowSQL
	2. COPY INTO to load data from internal stage to Database
3.  To unload:
	1. Use COPY into from database to internal storage
	2. Use GET command in snowSQL
4. 3 Type:
	1. User Stage
		1. Tied to 1 user
		2. Cannot be accessed by other users
		3. Every user has default stage
		4. Cannot be altered or modified
		5. Put files before loading
		6. Explicitly remove files again - Best Practice
		7. Can load data to multiple tables
		8. referred by '@~' sign
	2. Table Stage
		1. Automatically created when a table is created
		2. Can only be accessed by that 1 table
		3. Cannot be altered or dropped
		4. Load to one table
		5. referred to '@%TABLE_NAME'
	3. Internal Named Stage
		1. CREATE STAGE:
		2. Snowflake database object
		3. Everyone with privileges can access it
		4. Most flexible
		5. Referred to with '@STAGE_NAME'