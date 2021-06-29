[Home](../../README.md) > 
[Docker](../README.md) >
[Docker Compose](docker-compose.md) >
Docker Compose Commands

# Docker Compose Commands

For complete **Docker Compose CLI** commands information, visit https://docs.docker.com/compose/reference/

Compose has commmands for managing the whole lifecycle of your application:

    docker compose --help

## Start, stop, and rebuild services:

- **Build**:
    ```
    docker compose build
    ```

    More `docker compose build` command parameters:
    ```
    docker compose build --help
    ```

- **Start**:
    ```
    docker compose up
    ```

    More `docker compose up` command parameters:
    ```
    docker compose up --help
    ```

- **Stop**:
    ```
    docker compose down
    ```

    More `docker compose down` command parameters:
    ```
    docker compose down --help
    ```

## View the status of running services:

- **List containers**:
    ```
    docker compose ps
    ```

    More `docker compose ps` command parameters:
    ```
    docker compose ps --help
    ```

- **List images used by the created containers**:
    ```
    docker compose images
    ```

    More `docker compose images` command parameters:
    ```
    docker compose images --help
    ```

- **List running compose projects**:
    ```
    docker compose ls
    ````

    More `docker compose ls` command parameters:
    ```
    docker compose ls --help
    ```

- **Display the running processes**:
    ```
    docker compose top
    ```

    More `docker compose top` command parameters:
    ```
    docker compose top --help
    ```

## Stream the log output of running services:

- **Show logs output**:
    ```
    docker compose logs
    ```

    More `docker compose logs` command parameters:
    ```
    docker compose logs --help
    ```

## Run a one-off command on a service:

- **Run a one-off command**:
    ```
    docker compose exec SERVICE COMMAND
    ````

    Example:
    ```
    docker compose web sh
    ```

    More `docker compose exec` command parameters:
    ```
    docker compose exec --help
    ```

