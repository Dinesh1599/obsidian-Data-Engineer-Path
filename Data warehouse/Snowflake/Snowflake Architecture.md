Unlike [[Traditional Architecture]], snowflake has a combination of the best of both shared disk and shared nothing architecture called multi-clustered Shared Data

![[Pasted image 20251028191231.png]]
Benefits:
	1. Data Sharing
	2. Failover Capabilities
	3. Scalabilities
	4. Scalability
	5. Performance


![[Pasted image 20251028191332.png]]

1. Interoperable Storage
	1. Data can be unstructured, semi-structured and structured
	2.  stored in a scalable cloud storage service configured on s3, google cloud and azure blob
	3. data is stored in an internally optimized, compressed and columnar format(parquet?)
	4. data is encrypted in AES 256bit
	
2. Elastic Compute
	1. Complex tasks such as Loading and unloading, Analytics, Data Pipelines and ML model scoring and training are done
	2.  They are done in Virtual Warehouses. 