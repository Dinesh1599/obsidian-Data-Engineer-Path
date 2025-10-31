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
	2. Table Stage
	3. Internal Named Stage