Describing the distribution of a columns value.

Pruning: The concept of removed the micro-partitions that is not required during the query process.

What snowflake does with Clustering:
They maintain the following metadata of the micro-partition in a table:
1. No: of micro-partitions
2. No: of overlapping micro-partitions
3. Depth of the overlapping micro-partitions