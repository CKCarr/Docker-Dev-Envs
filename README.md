# Docker-Dev-Envs
This repository is intended to store files and configurations related to a development environments that utilize Docker containers.

You can use Docker Compose within each named environment directory to define and manage multiple containers specific to that environment. This approach allows you to create a comprehensive development environment for each "named-env" project.

You can structure a "named-env" directory with multiple containers managed by Docker Compose:

The idea is for my tree to look similar to the following with each named env to have the related files seperated into their own folders for future use and for collaboration. Combining this Repository, Dockerhub, and VSCode should benefit in documentation and hands-on learning.

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

-    Each "named-env" directory represents a different development environment.
-    Inside each "named-env" directory, you have subdirectories for individual containers (e.g., "container1," "container2").
-    Each "containerX" directory contains its Dockerfile and associated files.

You can define a unique docker-compose.yml file within each "named-env" directory to manage the containers for that specific environment. This allows you to create and manage a customized development environment with multiple containers tailored to the needs of the "named-env" project.

To start a specific environment, navigate to its directory (e.g., "named-env1") and use Docker Compose to build and start the containers defined in its docker-compose.yml file:

```
cd docker-dev-envs/named-env1
docker-compose up --build
```

This way, you can create and manage isolated development environments, each with its set of containers, configurations, and dependencies, within your repository.
