Copy Options defines how data is loaded and unloaded into the database
==Copy options will overwrite the stage copy options.==

List of Copy Options:

1. ON_ERROR = CONTINUE
	1. Continue loading file if error are found
	2. SKIP_FILE: 
		1. Skips file if errors are found (Default for snowpipe)
	3.  SKIP_FILE_<num>: 
		1. Skips file when the no: of errors >= <num>
	   4. SKIP_FILE_<num>%: 
		 1. Skips file when the no: of errors >= <num>%
	   5. ABORT_STATEMENT
		1. Aborts load if error is found. (Default on bulk load)
2. SIZE_LIMIT = <num>
	1. Specifies max. size of the data loaded
	2. Default: null
3. PURGE = TRUE | FALSE
	1. Deletes the file from the stage after loading
	2. Default: FALSE
4. MATCH_BY_COLUMN_NAME = CASE_SENSITIVE | CASE_INSENSITIVE | NONE
	1. Load semi-structured data columns by matching field names.
	2. Default: None
5. ENFORCE_LENGTH = TRUE | FLASE
	1. For checking the length of a value is beyond the defined column value.
	2. TRUE: Produces error if loaded string length is exceeded
	3. FALSE: Strings are automatically truncated



![[Pasted image 20251124163937.png]]



# UNLOADING

1. SINGLE = FALSE - Splits into multiple files (Default) | TRUE - One big file
2. MAX_FILE_SIZE = <num> - default = 16777216 (16mb) with max 5GB
3. FILE_FORMAT  = (TYPE = JSON) - File format can be set in the COPY command
4. HEADER = TRUE - Will include a header in the output file
5. OVERWRITE = 'ABORT_STATEMENT' - tells if its ok to overwrite existing files with matching names.


