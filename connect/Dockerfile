# https://github.com/debezium/container-images/tree/main/connect
# https://hub.docker.com/r/debezium/connect/tags
FROM jojoooo1/debezium-base-with-confluent:2.4.0-31341

ENV DEBEZIUM_VERSION="2.4.0.Final" \
    MAVEN_REPO_CENTRAL="" \
    MAVEN_REPOS_ADDITIONAL="" \
    MAVEN_DEP_DESTINATION=$KAFKA_CONNECT_PLUGINS_DIR \
    # MONGODB_MD5=87ab8a260c73150267ba8e7822d50c55 \
    # MYSQL_MD5=47d80c6955923deb7823c8c6c352864b \
    POSTGRES_MD5=b42c9e208410f39ad1ad09778b1e3f03 \
    # SQLSERVER_MD5=9635b79adbfb1cb7bd97a67781286b76 \
    # ORACLE_MD5=39fd3e04d7c6d2189f5284ccd7b44db8 \
    # DB2_MD5=a432aef71031629d00b6fc7d9f8a06e4 \
    # SPANNER_MD5=47958385e1c146d5b1487a35acf8f774 \
    # VITESS_MD5=150502404cd97e55e4646f2ebc7778ef \
    JDBC_MD5=77c5cb9adf932ab17c041544f4ade357 \
    KCRESTEXT_MD5=25c0353f5a7304b3c4780a20f0f5d0af \
    SCRIPTING_MD5=53a3661e7a9877744f4a30d6483d7957

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