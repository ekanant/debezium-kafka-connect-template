
## create connectors
```sh
curl -i -X POST -H "Accept:application/json" -H  "Content-Type:application/json" http://localhost:8083/connectors/ -d @sink.json
```


## edit connectors
```sh
curl -i -X PUT -H "Accept:application/json" -H  "Content-Type:application/json" http://localhost:8083/connectors/mongodb-sink/config --data-raw ' 
{ 
    "connector.class": "at.grahsl.kafka.connect.mongodb.MongoDbSinkConnector", 
    "tasks.max": "1", 
    "topics": "my_event_topic", 
    "mongodb.connection.uri": "mongodb://mongo_url@ip/database",
    "mongodb.collection": "my_collection", 
    "mongodb.document.id.strategy": "at.grahsl.kafka.connect.mongodb.processor.id.strategy.FullKeyStrategy", 
    "mongodb.delete.on.null.values": "true" 
}'
```