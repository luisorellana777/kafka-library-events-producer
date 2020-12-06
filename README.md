## Start Zookeeper and Kafka Broker

- Start up the Zookeeper.

```
cd ~/Documents/Applications/kafka_2.13-2.6.0/bin
./zookeeper-server-start.sh ../config/zookeeper.properties
```

- Add the below properties in the server.properties

```
listeners=PLAINTEXT://localhost:9092
auto.create.topics.enable=false
```

- Start up the Kafka Broker

```
./kafka-server-start.sh ../config/server.properties
```

## Create a topic

```
./kafka-topics.sh --create --topic test-topic -zookeeper localhost:2181 --replication-factor 1 --partitions 4
```

## Create a consumer

```
./kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic library-events --from-beginning
```

Sources: https://github.com/dilipsundarraj1/kafka-for-developers-using-spring-boot/blob/master/SetUpKafka.md