# Docker-Dev-Envs

This repository is intended to store files and configurations related to a development environments that utilize Docker containers.

You can use Docker Compose within each named environment directory to define and manage multiple containers specific to that environment. This approach allows you to create a comprehensive development environment for each "named-env" project.

You can structure a "named-env" directory with multiple containers managed by Docker Compose:

The idea is for my tree to look similar to the following with each named env to have the related files separated into their own folders for future use and for collaboration. Combining this Repository, Dockerhub, and VSCode should benefit in documentation and hands-on learning.

```
Docker-Dev-Envs/
├── docker-dev-envs/
│   ├── named-env1/
│   │   ├── container1/
│   │   │   ├── Dockerfile
│   │   │   ├── ...
│   │   ├── container2/
│   │   │   ├── Dockerfile
│   │   │   ├── ...
│   │   ├── Makefile
│   │   ├── README.md
│   │   ├── docker-compose.yml
│   ├── named-env2/
│   │   ├── container1/
│   │   │   ├── Dockerfile
│   │   │   ├── ...
│   │   ├── container2/
│   │   │   ├── Dockerfile
│   │   │   ├── ...
│   │   ├── Makefile
│   │   ├── README.md
│   │   ├── docker-compose.yml
│   ├── ...
```

In this structure:

- Each "named-env" directory represents a different development environment.
- Inside each "named-env" directory, you have subdirectories for individual containers (e.g., "container1," "container2").
- Each "containerX" directory contains its Dockerfile and associated files.

You can define a unique docker-compose.yml file within each "named-env" directory to manage the containers for that specific environment. This allows you to create and manage a customized development environment with multiple containers tailored to the needs of the "named-env" project.

To start a specific environment, navigate to its directory (e.g., "named-env1")

## To Build, Start, SSH, and create or clone inside container

Build the container by running:

```
make build
```

Start the container by running:

```
make run
```

SSH into the container by running:

```
make ssh
```

Once inside, clone the repository:

```
git clone [Your-Repository-URL]
```

You can also use Docker Compose to build and start the containers defined in its docker-compose.yml file:
If you are implementing a Docker compose to link containers together.

```
cd docker-dev-envs/named-env1
docker-compose up --build
```

This way, you can create and manage isolated development envir
onments, each with its set of containers, configurations, and dependencies, within your repository.

Data can be persisted in two main ways:

Bind mounts: These are basically mappings between the host filesystem and the container filesystem. Any changes made in the mapped directory in the container will reflect on the host filesystem.

Volumes: Docker-managed spaces that live outside the container filesystem but can be accessed by containers. These are useful for sharing data among multiple containers.

```
## Data Persistence

Data inside a Docker container does not persist after the container is deleted. However, you can use Docker volumes or bind mounts to persist data.

### Using Bind Mounts

In the `docker-compose.yml` or `Makefile`, you can add:


-v /path/on/your/computer:/path/in/container

```

This will map a directory from your host to the container, and data will persist.

Using Volumes
In your docker-compose.yml, you can define a volume:

```
services:
  your-service:
    volumes:
      - your-volume:/path/in/container
```

And then define your-volume at the bottom of the docker-compose.yml:

```
volumes:
  your-volume:
```

This way, the data in /path/in/container will be stored in a Docker-managed volume, and will persist even if the container is deleted.
