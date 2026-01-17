- Feature of snowflake which enables replicating databases between accounts within the org.

Syntax:
Alter Database DB_1
ENABLE REPLICATION TO ACCOUNTS ORG.account2;

- When a primary db is replicated a snapshot of the db's objects and data are transferred to the secondary db.

- The Secondary Database is refreshed by using
	- ATLER DATABASE REPLICA REFRESH;


Keep in mind

1. External Tables, Event Tables, Temporary Stages and Class Instances are currently not replicated
2. Refreshing a secondary database can be automated by configuring a task object to run the refresh command on a schedule
3. Refresh fails if a primary database contains an event or external table type.
4. Privileges are not replicated to the secondary db
5. Billing for database replication is based on data transfer and compute resource.