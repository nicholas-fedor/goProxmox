# ![Banner](/assets/images/banner.svg)

## A Proxmox manager written in Go

goProxmox is intended to be a sysadmin toolbox for people using the [Proxmox
Virtual Environment](https://www.proxmox.com/en/proxmox-virtual-environment/overview).

## Features

## Getting Started

### Prerequisites

- A running Proxmox host

> [Proxmox's Getting Started documentation](https://www.proxmox.com/en/proxmox-virtual-environment/get-started)

### Instructions

#### Quick Start via Docker Compose

> [Docker's Getting Started documentation](https://docs.docker.com/get-started/)

1. Create a directory for goProxmox:

    ```console
    mkdir goProxmox && cd goPromox
    ```

2. Download the Docker Compose script into the newly created directory:

    ```console
    wget github.com/nicholas-fedor/goProxmox/docker/docker-compose.yml
    ```

3. Run the application using the Docker Compose script:

    ```console
    docker compose up -d
    ```

4. Use your web browser to access the application's web GUI on port 8080 of your
   Docker host's IP address

#### Via a Proxmox LXC Container

## Tutorial

## Development

## Additional Documentation

- [Proxmox](https://pve.proxmox.com/pve-docs/)
- [Docker](https://docs.docker.com/manuals/)
- [Go](https://go.dev/doc/)

---
