 1. Cost is based on Compute and Storage separately
 2. i.e. Independently scalable
 3. pricing depends on region and cloud provider
 4. Data Transfer cost is also there

**Compute Cost:**
1. Charged only when the VH is active - mostly when query processing is done
2. Cloud services  - Behind the scene cloud service task - only charged if exceeds 10% VH compute consumption
3. Serverless - Search Optimization, snow pipe

Charges for compute:
1. Charged for active vh per hour (Billed by second) - min 1min
2. no of VH
3. size of vh
4. ==Charged in snowflake credits==


Credits:
	1. credits cost for the amount of vh running and the time of vh running
		1. xs  - 1 credit per hour
		2. s - 2 credits per hour
		3. M - 4 credits per hour 

Considering all this
1. Standard - $2 per credit
2. Enterprise - $3 per credit
3. Business Critical - $4 per credit
4. Virtual private - contact Sf

**Data Storage cost**
1. Monthly Storage fee
2. Based on avg storage used per month
3. ==cost is calculated after compression==
4. on demand storage - pay for what your use
5. Capacity storage - pay upfront for a defined storage.
Hence start with on-demand and understand then see capacity if needed

**Data Transfer Storage cost**
	1. Loading data in is free
	2. Loading data out is charged
		1. depends on region of data region used.