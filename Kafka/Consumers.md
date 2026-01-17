**Consumer** is an application that **subscribes to topics and reads events** from Kafka.

- Consumers **pull data** from Kafka (Kafka does not push)
    
- They track their position using an **offset**
    
- Consumers can **replay old data** by resetting offsets
    

Examples:

- A Spark/Flink job processing events
    
- A service updating a database
    
- A monitoring or alerting system
    

**Key idea:** Consumers read and process events at their own pace