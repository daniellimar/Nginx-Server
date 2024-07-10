# Nginx Server - Docker Project

This project sets up an Nginx web server using Docker. It provides a basic environment to host your web applications.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [License](#license)

## Prerequisites

Before you begin, ensure you have the following installed on your machine:

- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Installation

1. **Clone the Repository**

    ```bash
    git clone https://github.com/your-username/nginx-docker-project.git
    cd nginx-docker-project
    ```

2. **Build the Docker Image**

    ```bash
    docker-compose build
    ```

## Usage

1. **Start the Container**

    ```bash
    docker-compose up -d
    ```

   This command starts the container in detached mode. The Nginx server will be running and accessible on port 80.

2. **Stop the Container**

    ```bash
    docker-compose down
    ```

3. **View Logs**

   To view the logs of the running container, use:

    ```bash
    docker-compose logs -f
    ```

## Configuration

1. **Nginx Configuration**

   The Nginx configuration files are located in the `nginx` directory. You can modify the `nginx.conf` file to customize
   the server settings.

    ```bash
    nginx/
    └── nginx.conf
    ```

2. **Document Root**

   The default document root for the Nginx server is the `html` directory. Place your web application files in this
   directory.

    ```bash
    html/
    └── index.html
    ```

3. **Docker Compose File**

   The `docker-compose.yml` file defines the Docker services. You can modify this file to add more services or change
   the configuration.

    ```yaml
    version: '3'
    services:
      nginx:
        image: nginx:latest
        container_name: nginx-server
        volumes:
          - ./html:/usr/share/nginx/html
          - ./nginx/nginx.conf:/etc/nginx/nginx.conf
        ports:
          - "80:80"
    ```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
