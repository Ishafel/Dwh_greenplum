ARG NIFI_VERSION=2.8.0
FROM apache/nifi:${NIFI_VERSION}

ARG POSTGRES_JDBC_VERSION=42.7.10

USER root

RUN mkdir -p /opt/nifi/jdbc \
    && chown nifi:nifi /opt/nifi/jdbc \
    && chmod 755 /opt/nifi/jdbc

ADD --chown=nifi:nifi --chmod=0644 \
  https://repo1.maven.org/maven2/org/postgresql/postgresql/${POSTGRES_JDBC_VERSION}/postgresql-${POSTGRES_JDBC_VERSION}.jar \
  /opt/nifi/jdbc/postgresql.jar

USER nifi
