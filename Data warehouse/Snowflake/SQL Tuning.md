Database order of execution

Rows -> Groups -> Result
![[Pasted image 20251121200041.png]]

Query Spilling:
refers to "spilling" in Snowflake, a performance issue that happens when a query processes more data than can fit in the virtual warehouse's memory, causing intermediate results to be pushed to slower local and remote storage.

Where can spilling happen? 
1. Local Storage
2. Remote Disk
Fixes:
3. Limit data
4. Increase Warehouse size
5. 