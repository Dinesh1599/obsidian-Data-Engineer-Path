They are normally used to perform database operations. Mostly DELETE, UPDATE, INSERT

How is SP different from UDFs
1. UDFs does some sort of calculations and returns a value. SP need not do that
2. UDFs has to return a value. SP need not
3. SP can be called with the rights of the caller or the owner. UDFs need to have access to the objects reference to the function.

To create a SP
1. Snowflake Scripting. Snowflake SQL + procedural logic
2. JavaScript
3. Snowpark API

Query to create a SP:

CREATE PROCEDURE find_min (n1 int, n2 int )
	returns int  <-- ==must be specified even if nothing is returned==
	language sql
		as
		BEGIN
		if (n1 < n2)
			THEN RETURN n2
			ELSE RETURN N1
		end if;
		end;

Stored Procedures are schema level objects. Hence user level privileges can be given 

To call a SP use the query:
	CALL find_min (3, 2);

Best thing about SP:
	Can have multiple operations...


To make this more dynamic:
use :arguement
![[Pasted image 20251114022908.png]]
![[Pasted image 20251114022950.png]]

==Privileges are little scary but important here!!==

==EXECUTE AS CALLER is a good idea - Says run normally! - based on privileges given to that role==
==EXECUTE AS OWNER is sorta like telling the SP to run as admin==.

 ![[Pasted image 20251117201543.png]]