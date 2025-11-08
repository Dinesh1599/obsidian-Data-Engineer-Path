Standard Query:

COPY INTO [table_name]
FROM @STAGE_NAME;
FILES =  file_name (Optional)
COPY_OPTIONS (OPTIONALS)
FILE_FORMAT =(FORMAT_NAME = file_format_name | TYPE = CSV | JSON) (MUST HAVE)

Note: ==Patterns can also be used here instead of files with the help of [[Wildcard Characters]]==

Condition:
	1. Files must already be in the staged in:
		Internal or External Stage

Bulk Loading: Loading data into a table
Warehouse is needed. 
Data Transfer cost may vary - if the data where its loaded from is of a different region than where the account is based on.

[[File Formats]] (This in itself is a topic of its own): 
1. CSV
2. JSON
3. Parquet
4. AVRO
5. ORC
6. XML


Copy from table to stage:
  COPY INTO @Stage_Name;
  FROM [table_name]

