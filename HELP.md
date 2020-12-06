# Getting Started

cd ~/Documents/Applications/kafka_2.13-2.6.0/bin

./zookeeper-server-start.sh ../config/zookeeper.properties

./kafka-server-start.sh ../config/server.properties ./kafka-server-start.sh ../config/server-1.properties
./kafka-server-start.sh ../config/server-2.properties

./kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic library-events --from-beginning

curl -i \
-d '{"libraryEventId":null,"book":{"bookId":456,"bookName":"Kafka Using Spring Boot","bookAuthor":"Dilip"}}' \
-H "Content-Type: application/json" \
-X POST http://localhost:8080/v1/libraryevent