[Home](../../README.md) > 
[Docker](../README.md) >
Docker Compose

# Docker Compose

Compose is a tool for defining and running multi-container Docker applications. 

- **Overview of Docker Compose** - https://docs.docker.com/compose/

- **Install Docker Compose** - https://docs.docker.com/compose/install/

- **Get started with Docker Compose** - https://docs.docker.com/compose/gettingstarted/

Compose uses a YAML file to configure the application services.

Using Compose is a three-step process:

1. Define the application environment with a `Dockerfile` so it can be reproduced anywhere. [Dockerfile](dockerfile.md)

2. Define the services that make up your app in `docker-compose.yml` so they can be run together in an isolated environment. [Docker Compose YAML](docker-compose-yaml.md)

3. Run `docker compose up`and the Docker compose command starts and runs your entire app.

A `docker-compose.yml` YAML file looks like this:

    version: "3.9"
    services:
    web:
        build: .
        ports:
        - "5000:5000"
        volumes:
        - .:/code
        - logvolume01:/var/log
        links:
        - redis
    redis:
        image: redis
    volumes:
    logvolume01: {}

For more information about the **Compose file reference**, visit https://docs.docker.com/compose/compose-file/

