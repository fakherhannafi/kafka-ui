## PREREQUESITES
* if you are in windows you can install WSL2


## Install Java 17

```
apt install default-jre
```

## Install KAFKA 3.3.2 with Wget
```
wget https://downloads.apache.org/kafka/3.3.2/kafka_2.13-3.3.2.tgz

```

## Untar TGZ package
```
tar xzvf kafka_2.13-3.3.2
```

## Create symbolic link for kafka folder called current
```
ln -s kafka_2.13-3.3.2 current

```

## Launch Zookeeper 
Go to KAFKA HOME DIRECTORY
```
./bin/zookeeper-server-start.sh /srv/kafka/current/config/zookeeper.properties

```

## Launch KAFKA
Go to KAFKA HOME DIRECTORY
```
./bin/kafka-server-start.sh /srv/kafka/current/config/server.properties

```

## Create a topic
```
kafka-topics.sh --bootstrap-server localhost:9092 --topic firstTopic --create --partitions 3 --replication-factor 1
```

## Launch KAFKA UI
```
java -Dspring.config.additional-location=application-local.yml -jar kafka-ui-api-v0.5.0.jar
```

