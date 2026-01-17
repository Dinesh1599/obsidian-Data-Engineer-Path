A **partition** is a **subset of a topic** that stores events as an **ordered, append-only log**.

- Each topic is split into **one or more partitions**
    
- Events within a partition are **strictly ordered**
    
- Each partition is stored on **one broker at a time** (with replicas on others)
    

**Key idea:** A partition is the **unit of parallelism** in Kafka.

### **Why partitions exist**

Without partitions:
- Only one consumer could read a topic efficiently
    
- Throughput would be limited
    

With partitions:
- Data is **spread across brokers**
    
- Multiple consumers can process data **in parallel**