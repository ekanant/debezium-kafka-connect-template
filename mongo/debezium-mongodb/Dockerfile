FROM quay.io/debezium/connect:1.9.3.Final
ENV KAFKA_CONNECT_MONGODB_DIR=$KAFKA_CONNECT_PLUGINS_DIR/kafka-connect-mongodb

USER root
RUN microdnf -y install git maven wget && microdnf clean all

USER kafka

# Deploy Official MongoDB Sink Connector
RUN mkdir -p $KAFKA_CONNECT_MONGODB_DIR && cd $KAFKA_CONNECT_MONGODB_DIR && \
  wget "https://repo1.maven.org/maven2/org/mongodb/kafka/mongo-kafka-connect/1.7.0/mongo-kafka-connect-1.7.0-all.jar"