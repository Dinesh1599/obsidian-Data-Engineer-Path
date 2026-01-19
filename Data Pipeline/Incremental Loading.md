Incremental loading is loading only new or modified records since the last pipeline run, improving ETL efficiency, reducing compute cost, and enabling near real-time analytics.

Why is it used?
-  Only deltas are processed
- Pipelines run faster
- Costs are lower
- Data stays near-real-time

Best time to perform Incremental Loading

- Batch Increments
	- Why?
		- Minimizes impact on OLTP production systems
		- Reduces warehouse compute cost
		- Easier to manage failures
- Near-Real-Time
	- Why?
		- Business needs fresh data
		- Still avoids full streaming complexity
- Always (True Streaming)
	- Why?
		- Event-driven use case
		- Immediate reaction required.