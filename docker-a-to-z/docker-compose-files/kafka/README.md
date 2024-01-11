# Kafka

## Starting Kafka

### docker compose up

## Create a topic

### docker exec broker kafka-topics --bootstrap-server broker:9092 --create --topic TOPIC_NAME

## Describe topic
### kafka-topics --bootstrap-server kafka-broker-1:9092 --describe --topic userlog

## Write messages to the topic

### docker exec --interactive --tty broker kafka-console-producer --bootstrap-server broker:9092 --topic TOPIC_NAME

## Read messages from the topic

### docker exec --interactive --tty broker kafka-console-consumer --bootstrap-server broker:9092 --topic TOPIC_NAME --from-beginning

## Stop the Kafka broker

### docker compose down

## Check Kafka Version

### kafka-topics --version

## Working with kafka docker container

### docker exec -it docker-compose-kafka-broker-1-1 /bin/bash

### docker exec -it 4299c69d58c3 -f /var/log/broker.log

### docker exec -it b509cda072f9 /bin/bash

### docker exec -it docker-compose-kafka-broker-1-1 tail -f /var/log/broker.log

## Create bare minimum topic

### kafka-topics --create --bootstrap-server localhost:2181 --replication-factor 1 --partitions 1 --topic users

## Kafka Producer

### kafka-console-producer --broker-list kafka-broker-1:9092 --topic color-count-input

## Kafka Consumer

### kafka-console-consumer --broker-list kafka-broker-1:9092 --topic color-count-output

## Kafka Consumer

### kafka-console-consumer --bootstrap-server kafka-broker-1:9092 \

### --topic color-count-output \

### --from-beginning \

### --property print.key=true \

### --property print.value=true \

### --property key.deserializer=org.apache.kafka.common.serialization.StringDeserializer \

### --property value.deserializer=org.apache.kafka.common.serialization.LongDeserializer \

## List all topics

### kafka-topics --list --bootstrap-server kafka-broker-1:9092

## Create Compat Topic

### kafka-topics --bootstrap-server kafka-broker-1:9092 --create \

### --topic employee-salary-compact \

### --partitions 1 --replication-factor 1 \

### --config cleanup.policy=compact \

### --config min.cleanable.dirty.ratio=0.005 \

### --config segment.ms=10000

## Kafka Consumer(Compact)

### kafka-console-consumer --bootstrap-server kafka-broker-1:9092 \

### --topic employee-salary-compact \

### --from-beginning \

### --property parse.key=true \

### --property key.separator=,

## Kafka Producer(Compact)

### kafka-console-producer --bootstrap-server kafka-broker-1:9092 \

### --topic color-count-input \

### --property parse.key=true \

### --property key.separator=,

## Starting Kafkacat

### kafkacat -L -b localhost:19092

### docker run -it --network=host confluentinc/cp-kafkacat kafkacat -L -b localhost:19092

## Commands to monitor kafka clusters

### kafkacat -L -b localhost:19092

## Commands to check consumer

### kafkacat -C -b localhost:19092 -t twitter-topic

kafka-console-consumer --bootstrap-server 0.0.0.0:9092 --topic kRequests --from-beginning

111,{"Satish":"408"}
112,{"Shiva":"508"}
113,{"Ravi":"608"}
