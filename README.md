# Greenplum 6 + NiFi

Локальный Docker Compose стек с Greenplum 6 и Apache NiFi 2.8.0.

## Запуск

```bash
docker compose up -d --build
```

UI NiFi:

```text
https://localhost:8443/nifi
```

Дефолтные учетные данные из `.env.example`:

```text
admin / GreenplumNiFi123
```

В образ NiFi уже добавлен PostgreSQL JDBC-драйвер:

```text
/opt/nifi/jdbc/postgresql.jar
```

## Подключение к Greenplum из NiFi

Для controller service `DBCPConnectionPool` в NiFi используй:

```text
Database Connection URL: jdbc:postgresql://gpdb:5432/gpdb
Database Driver Class Name: org.postgresql.Driver
Database Driver Location(s): /opt/nifi/jdbc/postgresql.jar
Database User: gpadmin
Password: gpadminpw
```

Если поменяешь `GREENPLUM_DATABASE_NAME` или `GREENPLUM_PASSWORD`, укажи те же значения в NiFi.
