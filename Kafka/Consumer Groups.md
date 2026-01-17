A **consumer group** is a **set of consumers that work together to read data from one or more Kafka topics**, where **each partition is consumed by only one consumer within the group**.

### **Purpose of a consumer group**

Consumer groups exist to provide:

- **Parallel processing**
    
- **Scalability**
    
- **Fault tolerance**

### **How it works**

- ==Each consumer in the group is assigned **one or more partitions**==
    
- ==**No two consumers in the same group read the same partition**==
    
- If there are **more consumers than partitions**, extra consumers stay **idle**
    
- If there are **more partitions than consumers**, some consumers read **multiple partitions**


**What is the difference between [[Consumers]] and Consumer Groups**

|Aspect|Consumer|Consumer Group|
|---|---|---|
|What it is|Single consumer instance|Logical group of consumers|
|Parallelism|❌ None|✅ Yes|
|Fault tolerance|❌ No|✅ Yes (rebalancing)|
|Partition sharing|Not applicable|Partitions split among consumers|
|Scaling|Vertical only|Horizontal|
|Typical use|Simple or low-volume tasks|Production workloads|