# apigee-to-kafka-logging

There are many ways for sending Apigee transaction logs to Kafka. In this example, Kafka Proxy is used.

Manually install Kafka Proxy using tar file:

```
curl -O http://packages.confluent.io/archive/5.0/confluent-oss-5.0.1-2.11.tar.gz
tar -xzf confluent-oss-5.0.1-2.11.tar.gz
```

Edit "CONFLUENT-PATH/etc/kafka-rest/kafka-rest.properties" file as shown below:
  
```
bootstrap.servers=PLAINTEXT://KAFKA-IP:9092
listeners=http://0.0.0.0:8090
```

Start Kafka Proxy
```
bin/kafka-rest-start etc/kafka-rest/kafka-rest.properties
```

Apply service-callout.xml in Apigee API proxy definition and see the logs in Kafka.
