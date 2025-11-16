Supported format:
1. JSON
2. XML
3. Parquet
4. ORC
5. Avro


Data Structure in a JSON file:
	objects:  anything betweem {}
	Array: anything between []

Snowflake Caviar: VARIANT
	Can store data of any other datatype
	They store data is "null" string and not null as a value
	non-native strings(dates) are stored as strings
	max length is 16mb per row 

use case of VARIANT:
	Let snowflake convert semi-structured data int o hierarchy of ARRAY, OBJECT, and VARIANT data stored into VARIANT.

To create a [[File Formats]] for JSON:

CREATE FILE FORMAT my_file_format
TYPE = {JSON}


Loading a semi-structured data:

Standard Approach: ELT method


Extract and load Data -> Analyze/ Parse -> Flatten data



Querying a semi-structured Data:

select raw_column:courses
from variant_Table;

Issue: 

SELECT 
    RAW_FILE:id::int as id,  
    RAW_FILE:first_name::STRING as first_name,
    RAW_FILE:prev_company[0]::STRING as first_prev_company
FROM OUR_FIRST_DB.PUBLIC.JSON_RAW
UNION ALL 
SELECT 
    RAW_FILE:id::int as id,  
    RAW_FILE:first_name::STRING as first_name,
    RAW_FILE:prev_company[1]::STRING as second_prev_company
FROM OUR_FIRST_DB.PUBLIC.JSON_RAW
ORDER BY id;

When using something like this to flatten the JSON. its bad cuz we dont know how  many rows or elements will showup. use [[Snowflake Flatten data]]

Inserting Data into a JSON table

