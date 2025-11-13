Exact value can take time. But sometimes an approx value is good enough. thus getting this approx value can save so much time and use fewer resources. 

1. HLL() - Number of distinct values (DISCTINCT from SQL)
	1. Used whenever to count distinct values
	2. Basically resplaces SELECT COUNT(DISTINCT(ORDER_NAME));
	3. Very time saving
	4. Query:
		1. Select HLL(<column>) from 

2. APPROX_TOP_K() Frequent values
	1. Shows how many times the top values n values are present in the column.
	2.  Basically shows the top n values called along with the no: of times called.
	3. Present in JSON format!
	4. Query:
		1. select APPROX_TOP_K(<column>, n, <counter>)
	5. Note: the counter sections shows how high the accuracy is supposed to be. Basically how many distinct values the algorithm is allowed to track
		Therefore: higher the counter -> higher the accuracy, slower
		Lower the counter -> lower accuract, faster
	Also: counter must alwayays be >> n

3. APPROX_PERCENTILE() - Percentile values
	1. It’s basically the cutoff value at whatever percentile you choose.
	2. Query:
		1. SELECT APPROX_PERCENTILE(<column>,n)
			1. Where: n is the cut off value. for eg: if 0.5, shows 50% or if its 0.9, it shows the value of the 90% percentile

4. MINHASH + APPROXIMATE_SIMILARITY() - Similarity of 2 or more sets
	1. Uses MinHash to estimate the similarity between two or more datasets
	2. Uses Jaccards similarity coefficient as reference (J(A,B)=∣A∪B∣∣A∩B∣​)