2 ways

1. SHOW TABLES;
	1. Statistics for table storage and properties
2. TABLE_STORAGE_METRICS in information_schema  ( select * from our_first_db.information_schema.table_storage_metrics;)
	1. more detailed
		1. Active
		2. Time Travel
		3. Fail-safe
3. TABLE_STORAGE_METRICS in account_usage (select * from SNOWFLAKE.ACCOUNT_USAGE.TABLE_STORAGE_METRICS;)