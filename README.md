- Start it with `docker-compose up`. Once it boots, navigate to localhost:9000 in your browser. You should see the Kafdrop landing screen.
- Exec into the kafka container


  ```
   docker exec -it kafka-kafdrop_kafka_1 /bin/sh
   cd /opt/kafka/bin
  ```


- Run publisher to create some records 


```
   ./kafka-console-producer.sh --broker-list localhost:9092 --topic test
```



- Run subscriber to read those records on a different terminal window


```
   ./kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test --group test --from-beginning
```
