When data needs to be copied into a table
1. Upload the file into the internal stage
	1. Data is compressed into a .gz file
2. Use PUT command in snowSQL
3. COPY INTO to load data from internal stage to Database