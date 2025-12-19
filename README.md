# kafka-docker
Example of kafka docker setup

## Usage
```
# pull image and run as daemon
docker pull apache/kafka:3.9.1
docker run -d --name kafka-local -p 9092:9092 apache/kafka:3.9.1

# create a topic
docker exec -it kafka-local /opt/kafka/bin/kafka-topics.sh \
--create --topic test-topic --bootstrap-server localhost:9092

# list topic
docker exec -it kafka-local /opt/kafka/bin/kafka-topics.sh --bootstrap-server localhost:9092 --list


# produce messages
docker exec -it kafka-local /opt/kafka/bin/kafka-console-producer.sh \
--topic test-topic --bootstrap-server localhost:9092

# (type messages and press Enter)
{"c1":"v1"}

# consume messages
docker exec -it kafka-local /opt/kafka/bin/kafka-console-consumer.sh \
--topic test-topic --from-beginning --bootstrap-server localhost:9092
```

## Document
[Docker hub for Apache Kafka](https://hub.docker.com/r/apache/kafka/)  
[Apache Kafka Docker Doc](https://kafka.apache.org/41/getting-started/docker/)  
[Apache Kafka Quickstart](https://kafka.apache.org/41/getting-started/quickstart/)
 