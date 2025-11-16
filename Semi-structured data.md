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

