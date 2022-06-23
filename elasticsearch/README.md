## Reference
https://medium.com/dana-engineering/streaming-data-changes-in-mysql-into-elasticsearch-using-debezium-kafka-and-confluent-jdbc-sink-8890ad221ccf


## Command for create connector
```sh
curl -i -X POST -H "Accept:application/json" -H  "Content-Type:application/json" http://localhost:8083/connectors/ -d @sink.json
```
