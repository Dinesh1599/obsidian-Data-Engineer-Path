Process of creating a copy of an existing object in an Snowflake Account

Can Clone:
1. Database
2. Schema
3. Tables
4. Streams
5. Stages
6. File formats
7. sequences
8. tasks
9. Pipes

Cloning rules:

1. A cloned object does not retain any grants or privileges of the source. Except tables
2. Cloning is recursive for dB and Schemas
3. External tables and internal named stages are never cloned.
4. A cloned table does not contain history of source table
5. Temp and transient tables are cloned as temporary and trans tables.