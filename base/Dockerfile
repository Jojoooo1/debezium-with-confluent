FROM debezium/connect-base:2.3.2.Final

# WARNING DO NOT USE CONFLUENT_VERSION after 7.0.4 or it will throw error:
# Caused by: java.lang.ClassNotFoundException: com.google.common.util.concurrent.internal.InternalFutureFailureAccess

ENV CONFLUENT_VERSION=7.0.4 \
    AVRO_VERSION=1.10.1 \
    GUAVA_VERSION=31.0.1-jre

RUN docker-maven-download confluent kafka-connect-avro-converter "$CONFLUENT_VERSION" 0cfb290a8383db23d8fc9de64533c7a9 && \ 
    docker-maven-download confluent kafka-connect-avro-data "$CONFLUENT_VERSION" 63662cecdef9e9a82ec8c0817d3d8bc4 && \
    docker-maven-download confluent kafka-avro-serializer "$CONFLUENT_VERSION" 9d8cf9c8f2ddb17a5942648eb01d5e28 && \
    docker-maven-download confluent kafka-schema-serializer "$CONFLUENT_VERSION" 63f6849afcdbf917f709e5b1f8af1225 && \
    docker-maven-download confluent kafka-schema-registry-client "$CONFLUENT_VERSION" 7872ab3974f80ef40ffc92b9834cffa8 && \
    docker-maven-download confluent common-config "$CONFLUENT_VERSION" af49470c7255f562a8b8f202e106c118 && \
    docker-maven-download confluent common-utils "$CONFLUENT_VERSION" 59072fe942c91084537ce1c4092e415a && \
    docker-maven-download central org/apache/avro avro "$AVRO_VERSION" 35469fee6d74ecbadce4773bfe3a204c && \
    docker-maven-download central com/google/guava guava "$GUAVA_VERSION" bb811ca86cba6506cca5d415cd5559a7

