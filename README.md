# Infrastructure components

This project provides infrastructure components to run services such as databases, servers, and other utilities using Docker. Below, you'll find instructions on how to run these components.

- Databases
- Servers
- Utilities
- Other Infrastructure components

## Databases

To run any database, follow the general command structure below. Each database will have its own specific Docker Compose file and configuration.

### General Command

Replace **DOCKER_COMPOSE_FILE** with the appropriate Docker Compose file for your database.

``` sh
docker compose -f FOLDER/DOCKER_COMPOSE_FILE up -d
```

### Mysql Example

``` sh
docker compose -f mysql/docker-compose.mysql.yml up -d
```

## Available Databases

### Mysql

- Internal Port: `3306`
- External Port: `3307`

To run Mysql, execute:

``` sh
docker compose -f mysql/docker-compose.mysql.yml up -d
```

### Postgresql

The PostgreSQL setup includes PGAdmin for managing the database via a web interface.

- Internal Port: `5432`
- External Port: `5432`
- PgAdmin Access: <http://localhost:5050>

To run Mysql, execute:

``` sh
docker compose -f postgresql/docker-compose.postgresql.yml up -d
```

### Microsoft Sql Server

This setup involves several supporting files that help configure and initialize the SQL Server database.

#### Key Files

- **mssql/docker-compose.mssql.yml**: Defines the container for the SQL Server database.
- **mssql-db.Dockerfile**: Pulls the official Microsoft SQL Server image.
- **entrypoint.sh**: Configures the Microsoft SQL Server instance.
- **configure-db.sh**: Sets up database settings. To initialize a new database, uncomment the last line in this file.
- **setup.sql**: SQL script used to initialize the database name, schema and other database details.

#### Configuration

- Internal Port: `1433`
- External Port: `1433`

To run Mssql, execute:

``` sh
docker compose -f mssql/docker-compose.mssql.yml up -d
```
