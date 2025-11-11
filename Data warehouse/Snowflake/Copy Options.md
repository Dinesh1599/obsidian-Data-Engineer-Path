Copy Options defines how data is loaded and unloaded into the database
==Copy options will overwrite the stage copy options.==

List of Copy Options:

1. ON_ERROR = CONTINUE
	1. Continue loading file if error are found
2. SKIP_FILE: 
	1. Skips file if errors are found (Default for snowpipe)
3. SKIP_FILE_<num>: 
	1. Skips file when the no: of errors >= <num>
4. SKIP_FILE_<num>%: 
	1. Skips file when the no: of errors >= <num>%
5. ABORT_STATEMENT
	1. Aborts load if error is found. (Default on bulk load)
6. SIZE_LIMIT = <num>
	1. Specifies max. size of the data loaded
	2. Default: null
7. PURGE = TRUE | FALSE
	1. Deletes the file from the stage after loading
	2. Default: FALSE
8. MATCH_BY_COLUMN_NAME = CASE_SENSITIVE | CASE_INSENSITIVE | NONE
	1. Load semi-structured data columns by matching field names.
	2. Default: None
9. ENFORCE_LENGTH = TRUE | FLASE
	1. For checking the length of a value is beyond the defined column value.
	2. TRUE: Produces error if loaded string length is exceeded
	3. FALSE: Strings are automatically truncated