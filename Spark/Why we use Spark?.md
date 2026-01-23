1. In-memory computation
	1. Spark uses RAM to keep working data close to the CPU, avoiding disk IO whenever possible
	2. Only Active partitions or explicit cached datasets are stored and used.
	3. This is the main reason Spark is much faster than older system like Hadoop MapReduce.
2. [[Lazy Evaluation]]  
	1. Spark delays execution of transformations until an action is triggered, allowing it to optimize the full computation plan before processing data.
	2. Spark only **records instructions**, not processing data yet.
3. [[Fault Tolerance]] 
	1. if a task or executor fails, Spark uses DAG lineage to recompute only the lost data partitions and continues execution without restarting the job.
4. Partitioning
	1. Its the fundamental behavior behind spark. 
	2.  Partitions the data into parts and gives it to each executor (Worker Nodes)
