Types
1. Metadata Cache
2. Result Cache
3. Local Disk Cache


**Metadata Cache**
1. Present in the cloud service Layer 
2. holds object information and statistics
3. a.k.a metadata store
4. hold the information of important entities 
5. the tables created and which db they are in and micropartitions
6. Cuz of this, some queries doesnt even need WH computing
![[Pasted image 20251121231947.png]]

**Result Cache**
1. the results of queries often used is here. stored for upto 24hrs. 
2. the 24hrs gets extended every time the same query result is achieved for upto 31 days.
3. Note: To resume a result cache
	1. New query exactly matches previous query
	2. The underlying table data has not changed
	3. The same role is used as the previous query
	4. If time context function is used, the result cache is not used.

Local Disk Cache
