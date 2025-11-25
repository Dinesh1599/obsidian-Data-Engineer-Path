Concept of getting back the data the might've been deleted or truc'd.

Easily recoverable by the following syntax:

UNDROP TABLE <table_name>
			or
UNDROP DATABASE


Can also be cloned:
![[Pasted image 20251124194431.png]]

Retention Period:
1. Can be altered with DATA_RETENTION_TIME_IN_DAYS with the ALTER command
2. Default: 1 day.
3. Max: 90 (every editions except standard)
4. For temporary and transient table (Max 1) for all editions

Accessing Time Travel:
1. AT
2. BEFORE
3. UNDROP

**AT**
1. capture historical data inclusive of all changes made by a statement or transaction until that point
2. Parameters:
	1. OFFSET: how many seconds
	2. TIMESTAMP: a fixed date/time
	3. STATEMENT: by mentioning a statement ID

**BEFORE**
1. Captures historical data exclusive to that particular time.
2. Parameters:
	1. STATEMENT

**UNDROP**
1. Restores most recent version of a dropped table.