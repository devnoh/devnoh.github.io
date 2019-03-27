# KAFKA

## Basic
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

## Using 3 Brokers for Fault Tolerance
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

## Kafka UI

**Landoop**
Landoop enhances Kafka with User Interface, streaming SQL engine and cluster monitoring. It enables faster monitoring of Kafka data pipelines.

They provide a free all-in-one docker (LENSES Box) which can serve a single broker for up to 25M messages. Note that this is recommended for development environments.

**Confluent**
Another option is Confluent Enterprise which is a Kafka distribution for production environments. It also includes Control Centre, which is a management system for Apache Kafka that enables cluster monitoring and management from a User Interface.

**Yahoo Kafka Manager**
Kafka Manager is a tool for monitoring Kafka offering less functionality compared to the aforementioned tools.
* https://github.com/yahoo/kafka-manager

**KafDrop**
KafDrop is a UI for monitoring Apache Kafka clusters. The tool displays information such as brokers, topics, partitions, and even lets you view messages. It is a lightweight application that runs on Spring Boot and requires very little configuration.
* https://github.com/sehwannoh/Kafdrop

**LinkedIn Burrow**
Burrow is a monitoring companion for Apache Kafka that provides consumer lag checking as a service without the need for specifying thresholds. It monitors committed offsets for all consumers and calculates the status of those consumers on demand. An HTTP endpoint is provided to request status on demand, as well as provide other Kafka cluster information. There are also configurable notifiers that can send status out via email or HTTP calls to another service.
* https://github.com/linkedin/Burrow

**Kafka Tool**
Kafka Tool is a GUI application for managing and using Apache Kafka clusters. It provides an intuitive UI that allows one to quickly view objects within a Kafka cluster as well as the messages stored in the topics of the cluster. It contains features geared towards both developers and administrators.

If you cannot afford licenses, then go for Yahoo Kafka Manager, LinkedIn Burrow or KafDrop. Confluent's and Landoop's products are the best out there, but unfortunately, they require licensing.
