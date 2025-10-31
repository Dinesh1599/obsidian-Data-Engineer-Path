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
			1. Automatically have a minimum number of clusters and max clusters (Good for dy)