Kafka Brokers are servers that stores data in topics, manages message distribution to consumers. 

## Basic Understanding:

- Store and manage data
- Organizing into topics and partitions

Things that Kafka brokers can do:

1. Fault Tolerance
	1. Topic's partitions are distributed across multiple brokers
	2. Each partition has a leader broker and multiple replicas
	3. They have a retention policy as well.


# Types of Kafka Brokers


## Kafka Controller

The Kafka controller is the broker that manages cluster metadata, leader election, and failure handling, ensuring the cluster runs correctly.

The controller is in charge of **cluster-wide decisions**, including:

- **Leader election** for partitions
    
- Tracking **broker membership** (which brokers are alive)
    
- Managing **partition state** (leader, replicas, ISR)
    
- Handling **broker failures and recovery**
    
- Coordinating **rebalances** at the cluster level
    

**Key idea:**

> The controller is the **manager of the Kafka cluster**, not the data handler.
