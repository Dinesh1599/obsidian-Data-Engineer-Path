Tasks:
Used to Schedule execution of SQL statement / stored procedure.
Combined with streams to set up a continuous ETL workflows

Syntax:

Create task demo_task
	WAREHOUSE = warehouse_name
	SCHEDULE = '15 MINUTE'
	