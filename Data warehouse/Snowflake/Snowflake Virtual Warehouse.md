1. Provides  compute resources to execute queries and operations
2. Types
	1. Standard
	2. Snowpark-optimized (memory-intensive mostly for ML)
3. Sizes
4. Multi-cluster (Enterprise only)
	1. Where there is too much workload and the VH is unable process them quickly, they are auto-scaled by adding more clusters to balance the the load
	2. Great for more concurrent users.
	3. Not great for complex workload.
	4. Has 2 modes
		1. Maximized
			1. Always has the same amount of clusters.  (Good for static users)
		2. Auto Scaled
			1. Automatically have a minimum number of clusters and max clusters (Good for dynamic users)
	5. Scaling policy (when does snowflake use an additional cluster):
		1. Standard
			1. Favors staring additional VH
		2. Economy
			1. Favors conserving credits rather than starting additional WH

![[Pasted image 20251030204046.png]]

Virtual Warehouse Properties:
1. Can be created or dropped with queries
2. Can be suspended or resumed with queries.
3. they can be manually resized.
4. They can be clustered manually

![[Pasted image 20251121165834.png]]