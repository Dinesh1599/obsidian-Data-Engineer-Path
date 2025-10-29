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
	3.  Each Virtual Warehouse is a MPP cluster deployed on-demand
	4.  Scale Vertically  (Increase no: of compute resources)
	5. Scale Horizontally (increase concurrent users - think of it as being possible to do more different set of work)
	6. Payment
		1. Number of VH used
		2. How long they are run
		3. Size of each VH
	
3. Cortex AI
	1. Suite of AI features that uses LLMs to understand unstructured data and provide intelligent assistance
	2. Helps to build AI models with no code 
![[Pasted image 20251028193911.png]]
4. Cloud service layers
	1.  Brain of Snowflake - collection of services that coordinates and executes activities across the platform with VH
	2. Services
		1.  Authentication
		2. Infrastructure Management
		3. Metadata Management
		4. Query Parsing and Optimization
		5. Access Control
	3. retains metadata of how data has been used.
	4. makes it possible to create new VH in an instant.

5. Snowgrid
	1. Cross regional and cross cloud - allows users to collab on the same data data regardless of the cloud and region.


List of snowflake client options:
	1. Snowsigh
	2. SnowSQL
	3. Languagedrivers
	4. ODBC and JDBC drivers.
	5. snowflake SQL RESTApi

# Main Architecture

![[Pasted image 20251029131238.png]]

