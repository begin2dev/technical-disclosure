# MariaDB Docker Container

## Docker Container

https://hub.docker.com/_/mariadb

MariaDB Server is a high performing open source relational database, forked from MySQL

### Docker Compose Configuration

For more information about how to create a docker compose file, visit: [Docker Compose YAML](../../.docs/docker-compose-yaml.md)

    # Use root/mariadb as user/password credentials
    version: '3.8'

    services:
      db:
        image: mariadb
        restart: always
        environment:
          MYSQL_ROOT_PASSWORD: mariadb
        volumes:
          - mariadb_data:/var/lib/mysql
        ports:
        - 33061:3306

    volumes:
      mariadb_data:


### Docker Compose Build

    docker compose -f docker-compose.yml build --no-cache 

### Docker Compose Up (Start)

    docker compose -f docker-compose.yml up -d --remove-orphans

### Docker Compose Down (Stop)

    docker compose -f docker-compose.yml down -v --remove-orphans

### Docker Exec

    docker exec -it mariadb_db_1 /bin/bash

## MariaDB Commands

    mysql

    [Options]
        -h      Host
        -D      Database
        -u      Username
        -p      Password

### Connect to database

Connect to `localhost` database host with `user_name` user & prompt for password:

    mysql -u user_name -p

Connect to `db_host` database host with `user_name` user & prompt for password:

    mysql -h db_host -u user_name -p

Connect to `db_name` database at `db_host` database host with `user_name` user & prompt for password:

    mysql -h db_host -D db_name -u user_name -p

Connect to **db_name** database at **db_host** database host with **user_name** user and **user_pass** password:

    mysql -h db_host -D db_name -u user_name -p user_pass

### Show databases

    show databases;

Outputs:

    +--------------------+
    | Database           |
    +--------------------+
    | information_schema |
    | mysql              |
    | performance_schema |
    +--------------------+

### Change database

    use <db_name>

**Example**: Change to **mysql** database

    use mysql

Outputs:

    Database changed

### Get database tables

    show tables;

**Example**: Show `mysql` database tables

    show tables;

Outputs:

    +---------------------------+
    | Tables_in_mysql           |
    +---------------------------+
    | column_stats              |
    | columns_priv              |
    | db                        |
    | event                     |
    | func                      |
    | general_log               |
    | global_priv               |
    | gtid_slave_pos            |
    | help_category             |
    | help_keyword              |
    | help_relation             |
    | help_topic                |
    | index_stats               |
    | innodb_index_stats        |
    | innodb_table_stats        |
    | plugin                    |
    | proc                      |
    | procs_priv                |
    | proxies_priv              |
    | roles_mapping             |
    | servers                   |
    | slow_log                  |
    | table_stats               |
    | tables_priv               |
    | time_zone                 |
    | time_zone_leap_second     |
    | time_zone_name            |
    | time_zone_transition      |
    | time_zone_transition_type |
    | transaction_registry      |
    | user                      |
    +---------------------------+

### Exit database

    quit
