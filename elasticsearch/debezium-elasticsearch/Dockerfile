FROM quay.io/debezium/connect:1.9.3.Final
ENV KAFKA_CONNECT_ES_DIR=${KAFKA_CONNECT_PLUGINS_DIR}/confluentinc-kafka-connect-elasticsearch

USER root
RUN microdnf -y install git maven wget && microdnf clean all

USER kafka

# Create Sink connector
RUN mkdir -p ${KAFKA_CONNECT_ES_DIR} && cd ${KAFKA_CONNECT_ES_DIR} && \
   wget "https://d1i4a15mxbxib1.cloudfront.net/api/plugins/confluentinc/kafka-connect-elasticsearch/versions/13.1.0/confluentinc-kafka-connect-elasticsearch-13.1.0.zip" && \
  unzip confluentinc-kafka-connect-elasticsearch-13.1.0.zip && \
  mv confluentinc-kafka-connect-elasticsearch-13.1.0/lib/* ${KAFKA_CONNECT_ES_DIR} && \
  rm -rf confluentinc-kafka-connect-elasticsearch-13.1.0 \ 
  rm -f confluentinc-kafka-connect-elasticsearch-13.1.0.zip