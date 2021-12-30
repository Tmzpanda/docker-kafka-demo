# stackpath-kafka-demo
### Enviroment setup
- `docker-compose.yml` contains the steps of local kafka instance setup
- Use below command to create the topic    
`./bin/kafka-topics.sh --create --zookeeper zookeeper:2181 --replication-factor 1 --partitions 1 --topic stackpath-interview-homework` 

### Demo code of Kafka producer and consumer:
- In [`producer.py`](https://github.com/Tmzpanda/stackpath-kafka-demo/blob/master/producer.py) file,
  - `generate_event` function is to generate json events with fields of `eventID`, `eventTimestamp` and `eventSequence`
  - `producer` is a instance of `KafkaProducer` which publish json events to the topic
  
- In [`consumer.py`](https://github.com/Tmzpanda/stackpath-kafka-demo/blob/master/consumer.py) file,
  - `consumer` is a instance of `KafkaConsumer` which consumes from the topic
  - `transform` function is to transform the received message into a comma delimited line with expected fields
  - `append_to_file` function is to append the transformed records to the output file [`stackpath-homework-output.txt`](https://github.com/Tmzpanda/stackpath-kafka-demo/blob/master/temp/stackpath-homework-output.txt)
 

  


