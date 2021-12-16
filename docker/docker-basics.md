# Docker Basics

-   [Docker Desktop](#docker-desktop)
    -   [Download and install Docker Desktop](#download-and-install-docker-desktop)
    -   [Configure Docker Desktop](#configure-docker-desktop)
-   [Docker Engine](#docker-engine)
    -   [Docker Engine Installation](#install-docker-engine)
-   [Docker Compose](#docker-compose)
    -   [Install Docker Compose](#install-docker-compose)


## Docker Desktop

**Docker Desktop** is an easy-to-install application for your Mac or Windows environment that enables you to build and share containerized applications and microservices.

Docker Desktop includes:
-   **Docker Engine**
-   **Docker CLI client**
-   **Docker Compose**
-   Docker Content Trust
-   Kubernetes
-   Credential Helper.

Docker Desktop works with your choice of development tools and languages and gives you access to a vast library of certified images and templates in **Docker Hub**. This enables development teams to extend their environment to rapidly auto-build, continuously integrate, and collaborate using a secure repository.

Some of the key features of Docker Desktop include:
-   Ability to containerize and share any application on any cloud platform, in multiple languages and frameworks
-   Easy installation and setup of a complete Docker development environment
-   Includes the latest version of Kubernetes
-   Automatic updates to keep you up to date and secure
-   On Windows, the ability to toggle between Linux and Windows Server environments to -  build applications
-   Fast and reliable performance with native Windows Hyper-V virtualization
-   Ability to work natively on Linux through WSL 2 on Windows machines
-   Volume mounting for code and data, including file change notifications and easy access to running containers on the localhost network
-   In-container development and debugging with supported IDEs

**Source**
-   [**Docker Docs** Docker Desktop](https://docs.docker.com/desktop/) (_external link_)

### Download and install Docker Desktop

Docker Desktop is available for Mac and Windows. For download information, system requirements, and installation instructions, see:

-   [Install Docker Desktop on Mac](https://docs.docker.com/desktop/mac/install/) (_external link_)

-   [Install Docker Desktop on Windows](https://docs.docker.com/desktop/windows/install/) (_external link_)

### Configure Docker Desktop

To learn about the various UI options and their usage, see:

-   [Docker Desktop for Mac user manual](https://docs.docker.com/desktop/mac/) (_external link_)
-   [Docker Desktop for Windows user manual](https://docs.docker.com/desktop/windows/) (_external link_)


## Desktop Engine

**Docker Engine** is an open source containerization technology for building and containerizing your applications. Docker Engine acts as a client-server application with:
-   A server with a long-running daemon process dockerd.
-   APIs which specify interfaces that programs can use to talk to and instruct the Docker daemon.
-   A command line interface (CLI) client docker.

The CLI uses Docker APIs to control or interact with the Docker daemon through scripting or direct CLI commands. Many other Docker applications use the underlying API and CLI. The daemon creates and manage Docker objects, such as images, containers, networks, and volumes.

**Source**
-   [**Docker Docs** Docker Engine](https://docs.docker.com/engine/) (_external link_)

### Install Docker Engine

The installation section shows you how to install Docker on a variety of platforms:

-   [Install Docker Engine](https://docs.docker.com/engine/install/) (_external link_)


## Docker Compose

**Compose** is a tool for defining and running multi-container Docker applications. With Compose, you use a YAML file to configure your application’s services. Then, with a single command, you create and start all the services from your configuration.

Compose works in all environments: production, staging, development, testing, as well as CI workflows.

Using Compose is basically a three-step process:

1.  Define your app’s environment with a `Dockerfile` so it can be reproduced anywhere.

2.  Define the services that make up your app in `docker-compose.yml` so they can be run together in an isolated environment.

3.  Run `docker compose up` and the Docker compose command starts and runs your entire app. You can alternatively run `docker-compose up` using the docker-compose binary.

A `docker-compose.yml` looks like this:

    version: "3.9"  # optional since v1.27.0
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

For more information about the Compose file, see the [Compose file reference](https://docs.docker.com/compose/compose-file/) (_external link_).

Compose has commands for managing the whole lifecycle of your application:
-   Start, stop, and rebuild services
-   View the status of running services
-   Stream the log output of running services
-   Run a one-off command on a service

**Source**
-   [**Docker Docs** Docker Compose](https://docs.docker.com/compose/) (_external link_)

### Install Docker Compose

You can run Compose on macOS, Windows, and 64-bit Linux.

Docker Compose relies on Docker Engine for any meaningful work, so make sure you have Docker Engine installed either locally or remote, depending on your setup.
-   On desktop systems like Docker Desktop for Mac and Windows, Docker Compose is included as part of those desktop installs.
-   On Linux systems, first install the Docker Engine for your OS, then install Compose on Linux systems.

Follow the instructions to install Compose on Mac, Windows, Windows Server 2016, or Linux systems, or find out about alternatives like using the `pip` Python package manager or installing Compose as a container:
-   [Install Docker Compose](https://docs.docker.com/compose/install/#install-compose) (_external link_)
