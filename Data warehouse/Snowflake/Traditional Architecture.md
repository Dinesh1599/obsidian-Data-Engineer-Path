[Shared-Disk](https://www.geeksforgeeks.org/system-design/shared-disk-architecture-system-design/)

![[Pasted image 20251028185433.png]]

1. Shared Disk Architecture is a system design approach where multiple computers (nodes) access the same centralized disk storage simultaneously.

2. Advantage:
	1. **Scalability:** Easy to add new nodes for increased workload without massive infrastructure changes.
	2. **High Availability:** Storage remains accessible even if some nodes fail, ensuring continuous service.
	3. **Simplified Data Management:** Centralized storage makes backups, replication, and recovery easier.
	4. **Resource Efficiency:** Reduces data duplication, improves utilization, and simplifies overall data consistency.

3. Design principle
	1. ==Redundancy (multiple network/storage paths to minimize failure risk)==
	2. Data consistency (coordination protocols like Paxos or Raft, atomic operations)
	3. ==Scalability (framework for adding nodes/storage)==
	4. Security (access control and encryption)
	5. ==High availability (failover mechanisms)==
	6. Concurrency control (sophisticated algorithms to manage simultaneous access)

4. Challenges:
	1. Costs more and can get complicated.
	2. Risk of “traffic jams” if too many try to use the disk at once.
	3. More care needed to keep data in sync and avoid conflicts.

5. Where is it used?
	1. Big databases like Oracle RAC.
	2. Virtual machines and cloud systems (VMware).
	3. High-performance applications where many need the same data.
	4. Database clustering
	5. Enterprise applications (ERP/CRM)

[Shared Nothing Architecture](https://www.geeksforgeeks.org/system-design/shared-nothing-architecture/)
![[Pasted image 20251028185507.png]]
1. Shared Nothing Architecture (SNA) is a distributed computing design where each node (or server) operates independently, with its own CPU, memory, and storage, communicating only over the network. The nodes do not share memory or disk, ensuring no single point of contention.

2. Advantage:
	1. Horizontal Scalability: Easily scaled by adding more nodes without disrupting existing operations.
	2. Fault Isolation & Reliability: Failure of one node does not affect others, leading to high reliability and availability.
	3. Performance: Enables parallel processing; each node handles its own workload, reducing bottlenecks.
	4. Maintenance: Nodes can be updated or maintained independently, minimizing system downtime.
	5. Cost-Efficiency: Start small and grow as needed, optimizing costs.
	6. Resource Optimization: No resource contention as each node uses its own CPU, memory, and disk storage.

3. Design principle
	1. Full Independence: Each node manages its own CPU, memory, and storage, with no shared hardware or data.
	2. No Shared Resource Contention: There are no common bottlenecks because resources are not shared between nodes.
	3. Network-Based Communication: Nodes interact only through the network when needed to coordinate or transfer data.

4. Challenges
	1. Difficult to Design: Setting everything up so nodes work fully on their own takes careful planning.
	2. Hard to Keep Data in Sync: Making sure all nodes have the right, up-to-date data can be tricky.
	3. Network Issues Matter: If there are problems or delays in network communication, performance can drop.
	4. Balancing Workload: It’s not easy to make sure each node has just the right amount of work and data.
	5. Recovering from Failures: When a node fails, getting things running smoothly again is more complex.

5. Where is it used?
	1. Distributed Databases: Systems like Cassandra, DynamoDB, and Google Spanner use it to store and process huge amounts of data across many independent nodes.
	2. Content Delivery Networks (CDNs): Networks like Akamai and Cloudflare use it to deliver web content from multiple locations quickly.
	3. Cloud Platforms: Services such as AWS and Azure use it for scaling servers and storage easily and reliably.

| Feature          | Shared Disk                      | Shared Nothing                |
| ---------------- | -------------------------------- | ----------------------------- |
| Data Storage     | Centralized for all nodes        | Partitioned by node           |
| Scalability      | Limited by disk capacity/I/O     | Highly scalable               |
| Data Consistency | Easier with single pool          | Requires complex coordination |
| Fault Tolerance  | Risk of single disk failure      | Node failures are isolated    |
| Performance      | May hit I/O bottlenecks          | Distributed workload          |
| Complexity       | More complex concurrency control | Complex partitioning          |
