How does snowflake know which is the file format is needed to load

When running the query: ==DESC STAGE db.schema.stage_name==, There is a property called "property_type" and "property_default". If "property_type" is not provided, "property_default" is taken into consideration.

![[Pasted image 20251107200507.png]]

Possible to overrule with the following:
file_format (type = [the_file_type]);

Stage object Metadata:
STAGE_FILE_FORMAT, 
STAGE_COPY_OPTIONS, 
STAGE_LOCATION

==but there is an option to predefine this metadata with values (IMPORT)==
- ==This makes it possible to use the same file_format for multiple stages.==

CREATE FILE FORMAT <fileformatname>
	TYPE = CSV
	FILE_DELIMITER = ','
	SKIP_HEADER = 1

then use this when creating the stage

CREATE STAGE <stagename>
URL = '<location>'
FILE_FORMAT = (FORMAT_NAME = <fileformatname>)
