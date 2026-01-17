Kafka is setup here with the official confluent kafka image in the [[docker-compose]] file.

## Conventional setup:

```yml
version: '3.8'

services:
  kafka:
    image: confluentinc/cp-kafka:7.8.3
    container_name: kafka
    ports:
      - "9092:9092"

    environment:
      KAFKA_KRAFT_MODE: 'true'

      CLUSTER_ID: '1L6g7nGhU-eAKfL--X25wo'
      KAFKA_NODE_ID: 1

      KAFKA_PROCESS_ROLES: broker,controller
      KAFKA_CONTROLLER_QUORUM_VOTERS: 1@kafka:9093
      KAFKA_OFFSETS_TOPIC_REPLICATION_FACTOR: 1 #important

      KAFKA_LISTENERS:
	      PLAINTEXT://0.0.0.0:9092,
	      CONTROLLER://0.0.0.0:9093
      KAFKA_ADVERTISED_LISTENERS: PLAINTEXT://localhost:9092
      KAFKA_CONTROLLER_LISTENER_NAMES: CONTROLLER

      KAFKA_LOG_DIRS: /tmp/kraft-combined-logs

    volumes:
      - kafka_kraft:/var/lib/kafka/data

volumes:
  kafka_kraft:
``` 


Environment setup explained:

CLUSTER_ID:
	Tells which cluster this broker belongs to

KAFKA_NODE_ID:
	Gives an identifier for that node in the cluster.

| Environment                                  | Purpose                                       | Type      |
| -------------------------------------------- | --------------------------------------------- | --------- |
| KAFKA_KRAFT_MODE:                            | To enable Kafka's Kraft (true)                | Boolean   |
| CLUSTER_ID                                   | Random String                                 | String    |
| KAFKA_NODE_ID:<br>                           | The broker identifier                         | int       |
| KAFKA_PROCESS_ROLES: <br>                    | Broker, Controller                            |           |
| KAFKA_CONTROLLER_QUORUM_VOTERS: <br>         | Raft consensus members                        |           |
| KAFKA_OFFSETS_TOPIC_REPLICATION_FACTOR: <br> | Replication factor for consumer offset topics | important |
| KAFKA_LISTENERS: <br>                        | Where Kafka Listens                           |           |
| KAFKA_ADVERTISED_LISTENERS:                  | How clients listens                           |           |
| KAFKA_CONTROLLER_LISTENER_NAMES: <br>        | How Controllers listens                       |           |
| KAFKA_LOG_DIRS:<br>                          | Tells Kafka where the logs are saved          |           |


