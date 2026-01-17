Describing the distribution of a columns value.

Pruning: The concept of removed the micro-partitions that is not required during the query process.

What snowflake does with Clustering:
They maintain the following metadata of the micro-partition in a table:
1. No: of micro-partitions
2. No: of overlapping micro-partitions
3. Depth of the overlapping micro-partitions

Overlapping micro-partitions and its depth eg:

![[Pasted image 20251123132206.png]]

Observation:
	Higher the clustering overlap and depth, the worse the clustering is.


Automatic Clustering:
	Requires a Clustering key (A unique column in the table). Depending on that data in the column, snowflake automatically sorts the data and arranges them in the correct cluster.
	Clustering improves performance on tables where queries include WHERE JOIN ORDER BY and GROUP BY (basically Filters)
	Larger the table data, clustering is more useful (>1TB)

Choosing a Cluster Key:
1. Max 3 or 4 columns per key. Recommended 3 to 4 MAX
2. Common columns when used on filtering or sorting.
3. Cardinality of Clustering Key.