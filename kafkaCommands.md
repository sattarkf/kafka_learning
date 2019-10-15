#Kafka Commands

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


