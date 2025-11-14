They are normally used to perform database operations. Mostly DELETE, UPDATE, INSERT

How is SP different from UDFs
1. UDFs does some sort of calculations and returns a value. SP need not do that
2. UDFs has to return a value. SP need not
3. SP can be called with the rights of the caller or the owner. UDFs need to have access to the objects reference to the function.

To create a SP
1. Snowflake Scripting. Snowflake SQL + procedural logic
2. JavaScript
3. Snowpark API