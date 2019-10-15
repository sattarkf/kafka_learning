####Kafka Commands

### Setup Zookeeper
1) Create folder "data" in Kafka to hold the data
2) Copy full path of zookeeper data
	c:\Kafka\data\Zookeeper
3) Go to c:\Kafka\config and open zookeeper.properties
   replace dataDir=/tmp/zookeeper with c:/kafka/data/zookeeper

## How to Start Zookeeper
1) go to CMD and navigate to c:\kafka
	>zookeeper-server-start.bat config\zookeeper.properties
	 Verify INFO binding to port 2181 to confirm that zookeeper has been started successfully.

### Setup Kafka
1) Open another cmd terminal and edit server.properties file from Config
2) replace log.dirs=/tmp/kafka-logs with c:/kafka/data/kafka

## How to Start Kafka Server
1) go to CMD and navigate to c:\kafka
	>kafka-server-start.bat config\server.properties
	Verify [Kafka server id=0] started to confirm that Kafka server has been started successfully.



## Kafka Topic
1) kafka-topics
This command gives the documentation on Kafka topics with mandatory and essential options to create, delete, describe and change the topic.

2) kafka-topics --zookeeper 127.0.0.1:2181 --topic first_topic --create --partitions 3 --replication factor 1
This command is to create a new topic with mandatory options like partitions and replication factor.
# A topic cannot be created with replication factor greater than number of brokers

3) kafka-topics --zookeeper 127.0.0.1:2181 --list 
This command displays number of topics available in Kafka

4) kafka-topics --zookeeper 127.0.0.1:2181 --topic first_topic --describe
This command gives comprehensive details about the topic 
EX:
Topic: first_topic	PartitionCount: 3	Replication factor: 1	Configs:

Topic: first_topic	Partition: 0	Leader: 0	Replicas:0	ISR:0
Topic: first_topic	Partition: 1	Leader: 0	Replicas:0	ISR:0
Topic: first_topic	Partition: 2	Leader: 0	Replicas:0	ISR:0
					Here Leader ID is 0, since Broker ID is 0. Verify the information from logs, Broker=0

5) kafka-topic --zookeeper 127.0.0.1:2181 --topic second_topic --delete
This command will delete the topic from Kafka
# Currently, windows has a bug (Kafka-1194) and if this command is used then it will crash Kafka.
# Work Around: Manually delete the topic from folders under data/kafka.
# Topic won't be deleted if delete.topic.enable is NOT set to true (By default it will always be TRUE).



## Kafka Console Producer
1) kafka-console-producer
This command will give the documentation on producer with options and --broker-list, --topic are mandatory fields.
.bat can be used for windows and .sh for linux ex: kafka-console-producer.sh

2) kafka-console-producer --broker-list 127.0.0.1:9092 --topic first_topic
This command will allow to send messages to the topic name "first_topic" 
ex:
>hello
>learning kafka
# Press Ctrl+C to exit from console producer


3) kafka-console-producer --broker-list localhost:9092 --topic first_topic --producer-property acks=all
Producer-Property will helps to add additional options like acks
ex: >some message that is acked
























