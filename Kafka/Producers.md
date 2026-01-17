A **producer** is an application that **publishes (writes) events** to Kafka.

- It sends data **to a specific topic**
    
- It does **not know or care** who will read the data
    
- Examples:
    
    - A web app sending user click events
        
    - A service publishing transaction records
        

**Key idea:** Producers generate events and push them into Kafka.