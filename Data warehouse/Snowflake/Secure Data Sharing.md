Process of sharing a Read-Only view of objects across accounts in an org.

It is enabled with an account-level SHARE object. it is created by a data provider and consists of two key configs:
1. Grants on database objects
2. Consumer account defs.
   ![[Pasted image 20251124213204.png]]
Possible sharable thigns:
3. Tables
4. External tables
5. Secure Views
6. Secure Materialized views
7. Secure UDFs

Data consumer create a database from a SHARE which contains the read-only database objects granted by the data provider. 
![[Pasted image 20251124213546.png]]