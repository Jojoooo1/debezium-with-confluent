FROM jojoooo1/debezium-base-with-confluent:2.3.2-29674

ENV DEBEZIUM_VERSION="2.3.2.Final" \
    MAVEN_REPO_CENTRAL="" \
    MAVEN_REPOS_ADDITIONAL="" \
    MAVEN_DEP_DESTINATION=$KAFKA_CONNECT_PLUGINS_DIR \
    # MONGODB_MD5=87ab8a260c73150267ba8e7822d50c55 \
    # MYSQL_MD5=47d80c6955923deb7823c8c6c352864b \
    POSTGRES_MD5=37f441ec730dd770928b4219a9a79d21 \
    # SQLSERVER_MD5=9635b79adbfb1cb7bd97a67781286b76 \
    # ORACLE_MD5=39fd3e04d7c6d2189f5284ccd7b44db8 \
    # DB2_MD5=a432aef71031629d00b6fc7d9f8a06e4 \
    # SPANNER_MD5=47958385e1c146d5b1487a35acf8f774 \
    # VITESS_MD5=150502404cd97e55e4646f2ebc7778ef \
    JDBC_MD5=7f9297dd61a09379cb60cdc3e4f23ba0 \
    KCRESTEXT_MD5=c28e8184a234db32b4c32780ba789c10 \
    SCRIPTING_MD5=0726417249e59e375404c1b670e9a237

RUN docker-maven-download debezium postgres "$DEBEZIUM_VERSION" "$POSTGRES_MD5" && \
    # docker-maven-download debezium mongodb "$DEBEZIUM_VERSION" "$MONGODB_MD5" && \
    # docker-maven-download debezium mysql "$DEBEZIUM_VERSION" "$MYSQL_MD5" && \
    # docker-maven-download debezium sqlserver "$DEBEZIUM_VERSION" "$SQLSERVER_MD5" && \
    # docker-maven-download debezium oracle "$DEBEZIUM_VERSION" "$ORACLE_MD5" && \
    # docker-maven-download debezium-additional db2 db2 "$DEBEZIUM_VERSION" "$DB2_MD5" && \
    docker-maven-download debezium-additional jdbc jdbc "$DEBEZIUM_VERSION" "$JDBC_MD5" && \
    # docker-maven-download debezium-additional spanner spanner "$DEBEZIUM_VERSION" "$SPANNER_MD5" && \
    # docker-maven-download debezium-additional vitess vitess "$DEBEZIUM_VERSION" "$VITESS_MD5" && \
    docker-maven-download debezium-optional connect-rest-extension "$DEBEZIUM_VERSION" "$KCRESTEXT_MD5" && \
    docker-maven-download debezium-optional scripting "$DEBEZIUM_VERSION" "$SCRIPTING_MD5"