# kafka-streams

Step to use this kafka simple client

Prerequisite

- Download http://www-eu.apache.org/dist/kafka/1.1.0/kafka_2.11-1.1.0.tgz
- tar -xzf kafka_2.11-1.1.0.tgz
- cd kafka_2.11-1.1.0
- bin/zookeeper-server-start.sh config/zookeeper.properties
- bin/kafka-server-start.sh config/server.properties
- bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic transcations-input
- bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic transcations-output
- bin/kafka-topics.sh --list --zookeeper localhost:2181

- Through browser download source code from https://codeload.github.com/divang/kafka-streams/zip/master
- unzip kafka-streams-master.zip
- cd kafka-streams-master
- mvn clean install
- cd target
- java -cp .:streams-0.0.1-SNAPSHOT.jar com.training.kafka.basic.streams.SimpleStream

-To produce data to Stream source input topic:
	- bin/kafka-console-producer.sh --broker-list localhost:9092 --topic transcations-input

-To validate Stream sink output topic data:
	- bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic  transcations-output --from-beginning
