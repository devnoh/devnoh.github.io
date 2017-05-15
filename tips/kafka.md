# KAFKA

### Basic
```
$ tar zxvf kafka_2.12-0.10.2.1.tgz
$ cd kafka_2.12-0.10.2.1
```

Start Zookeeper Server:
```
$ bin/zookeeper-server-start.sh config/zookeeper.properties
```

Start Kafka Server:
```
$ bin/kafka-server-start.sh config/server.properties
```

Create Topic:
```
$ bin/kafka-topics.sh --zookeeper localhost:2181 --create --topic MyFirstTopic --partitions 2 --replication-factor 1
```

Delete Topic:
```
$ bin/kafka-topics.sh --zookeeper localhost:2181 --delete --topic MyFirstTopic
```

Create Console Producer:
```
$ bin/kafka-console-producer.sh --broker-list localhost:9092 --topic MyFirstTopic
```

Create Console Consumer:
```
$ bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic MyFirstTopic
```

### Using 3 Brokers for Fault Tolerance
```
$ cp server.properties server-1.properties
$ cp server.properties server-2.properties

$ vi server-1.properties
---
broker.id=1
listeners=PLAINTEXT://:9093
Log.dirs=/tmp/kafka-logs-1
---

$ vi server-2.properties
---
broker.id=2
listeners=PLAINTEXT://:9094
Log.dirs=/tmp/kafka-logs-2
---

$ bin/kafka-server-start.sh config/server-1.properties
$ bin/kafka-server-start.sh config/server-2.properties

$ bin/kafka-topics.sh --zookeeper localhost:2181 --create --topic TestTopicXYZ --partitions 2 --replication-factor 3
$ bin/kafka-topics.sh --zookeeper localhost:2181 --describe --topic TestTopicXYZ
---
Topic:TestTopicXYZ	PartitionCount:2	ReplicationFactor:3	Configs:
	Topic: TestTopicXYZ	Partition: 0	Leader: 0	Replicas: 0,1,2	Isr: 0,1,2
	Topic: TestTopicXYZ	Partition: 1	Leader: 1	Replicas: 1,2,0	Isr: 1,2,0
---
```
