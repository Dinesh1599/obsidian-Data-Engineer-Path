This command validates the files loaded in a past execution of the COPY INTO command and returns all the errors encountered during the load

==Doesn't return anything if ON_ERROR = ABORT_STATEMENT==

Query is written like this

```sql

VALIDATE( <table_name>, JOB_ID => {'<query_id>', | '_last' } )

```