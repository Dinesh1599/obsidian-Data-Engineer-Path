Tasks:
Used to Schedule execution of SQL statement / stored procedure.
Combined with streams to set up a continuous ETL workflows
It is a Schema Level Object

Syntax:

Create task demo_task
	WAREHOUSE = warehouse_name
	SCHEDULE = '15 MINUTE'
	AS
	INSERT INTO TABLE_NAME (VALUES);

Privileges needed to set up a task
1. Account Level = Execute Managed Task
2. Schema Level  = Create Task
3. Warehouse Level = Usage

To start a task 
ALTER task taskname RESUME
ALTER task taskname SUSPEND

Note: Run the above command to run the task that is created.

Tasks can also be directed... called Directed Acyclic Graph (DAG)

![[Pasted image 20251117031709.png]]

Setup:
Assuming we are setting up task A (reference to the image above):

CREATE TASK Task_A
WAREHOUSE = warehouseName
AFTER = Root_Task  <--------- mention the predecessor 
as 
...;

# Streams
It is a Schema Level Object
A Stream is used to record [[DML]] changes to a table
This process is called Change Data Capture CDC

Syntax:
	CREATE STERAM streamName
		ON TABLE tableYouNeedStreamFor;

Querying from a stream: 
	Select * from streamName;

Consuming a stream:
	So, the changed data is in the stream. Stream can be consumed. Meaning, if we use the stream data to update the table, it empties that data from the stream.


Types of Streams:
1. Standard Stream
	1. Supports
		1. Insert
		2. Update
		3. Delete
2. Append-only Stream
	1. Supports
		1. Insert
3. Insert-only Stream
	1. Supports
		1. Insert.

Difference in Append-only stream and insert-only stream:

Insert-only stream only works for external tables.
Append-only streams does not supports external tables but supports
1. Standard Tables
2. Directory Tables
3. Views

Stream Staleness
  