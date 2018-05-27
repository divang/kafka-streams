# kafka-streams
Stream setup:
bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic transcations-input
bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic transcations-output

to test
mvn clean install
cd target
java -cp .:streams-0.0.1-SNAPSHOT.jar com.training.kafka.basic.streams.SimpleStream

To produce data:
bin/kafka-console-producer.sh --broker-list localhost:9092 --topic transcations-input

To validate output:
bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic  transcations-output --from-beginning
