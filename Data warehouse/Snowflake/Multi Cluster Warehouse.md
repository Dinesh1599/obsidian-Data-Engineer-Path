Scaling up: Improve query performance...


When Resizing a Query:
1. Resizing a running WH does not impact the running queries. Additional queries are used for queued queries and new queries.
2. Decreasing the size will delete the WH cache and removes compute resources.


Scaling out (Multi-Cluster WH):
Groups of virtual WH that can automatically scale in and out based on the number of concurrent users/queries. 

Two properties:
1. MIN_CLUSTER_COUNT: specifies the minimum number of WH for a multi-cluster WH
2. MAX_CLUSTER_COUNT:specifies the maximum number of WH for a multi-cluster WH

Note: 
1. if MIN and MAX are the same: it will put the WH is MAXIMIZED mode
2. if both are different the multi-cluster WH is set to AUTO-SCALING mode

Scaling Policy:
	1. Standard
		1. Favors staring additional VH
	2. Economy
		1. Favors conserving credits rather than starting additional WH
![[Pasted image 20251030204046.png]]