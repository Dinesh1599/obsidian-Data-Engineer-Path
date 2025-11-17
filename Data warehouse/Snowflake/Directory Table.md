Stores metadata of an external staged files
Note: It is not a database object but a layer of stage object. Can be queried with sufficient privileges (on the [[Snowflake Stages]]).
Snowflake needs to track **files inside cloud storage**, which can change outside Snowflake.

### Purpose:
Track + detect + query file metadata stored _outside Snowflake_.

Where is this privileges enabled?

Syntax:
CREATE STAGE azure_stage
	url = <'url'>
	file_format = fileformat
	STORAGE_INTEGRATION  = INTEGRATION
	==DIRECTORY = (ENABLE = TRUE)==

To update an existing stage
ALTER STAGE azure_stage
	SET DIRECTORY  = (ENABLE = TRUE);

To query
Select * from DIRECTORY (@azure_stage) - Note: If this is done for the first time, nothing is seen...

Hence: run -> ALTER STAGE azure_stage REFRESH;

