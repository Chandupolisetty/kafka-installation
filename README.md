# KAFKA

## How to install KAFKA

Start the Kafka Environment

Open powershell as administrator and then follow the steps:

Run Zookeeper Service  (keep this open)
```
.\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties
```
Other window- Run Kafka Service (keep this open)
```
.\bin\windows\kafka-server-start.bat .\config\server.properties
```
New window- Create a topic(as you wish) to store all your data 
```
.\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --create --topic bearcat-messages
.\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --list
```
New window- Run Kafka Producer (will provide a > prompt for writing messages)
```
.\bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic bearcat-messages
```
New window- Run Kafka Consumer (to show messages from the beginning)
```
.\bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic bearcat-messages --from-beginning
```