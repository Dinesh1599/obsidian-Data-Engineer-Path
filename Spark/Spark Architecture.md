![[Pasted image 20260122225447.png]]


Spark works on a Cluster of Computers and Spark follows the Master-Slave Architecture.

Driver program: Responsible for running code and scheduling tasks on executors.

Executor Node: A JVM that perform the actual calculation and processing

Cluster Manager: The Cluster Manager is responsible to manage the resources(Clusters).

The understanding here:
	When a Driver Program executes Spark code, it contacts the Cluster Manager to request resources.  
	The Cluster Manager launches Executor JVMs on existing Worker Nodes.  
	Once Executors are running, the Driver sends tasks (each handling a data partition) to them.  
	The Worker Nodes execute these tasks in parallel and return results to the Driver.