UDF- User Defined Function
Adding functions to snowflake for your DB
Supported Languages:
1. SQL
2. JAVA
3. Python
4. JavaScript

Syntax:

For SQL:
	CREATE FUNCTION add_two (n int)
	returns <datatype>
	as
	$$
	n+2
	$$;

To call the function just mention it as SELECT add_two(3);

for something like python:

CREATE OR REPLACE FUNCTION addone(i INT)
  RETURNS INT
  LANGUAGE PYTHON
  RUNTIME_VERSION = '3.12'
  HANDLER = 'addone_py'
AS $$
def addone_py(i):
 return i+1
$$;

Note: The handler is what tells snowflake which function is called when running this UDF.