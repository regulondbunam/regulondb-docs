# Docker Installation Guide

This guide explains how to install and run a local RegulonDB instance using Docker.

## Source of Truth

- Official page: [https://regulondb.ccg.unam.mx/manual/apiSoftware/docker](https://regulondb.ccg.unam.mx/manual/apiSoftware/docker)

## Required Software

- Docker
- Docker Compose

## Installation Guide

1. Download or copy the content of the Docker configuration file as `docker-compose.yml`.
2. In a terminal, move to the folder where `docker-compose.yml` is located.
3. Pull the required images from DockerHub:

```bash
docker compose pull
```

4. Start the RegulonDB local instance:

```bash
docker compose up -d
```

## Access Endpoints

After startup, the instance is available at:

- Web app: `http://localhost:7000/`
- GraphQL Playground: `http://localhost:7000/graphql`

To stop the instance:

```bash
docker compose down
```

## New Releases

When a new release is available:

1. Repeat the installation steps with the updated `docker-compose.yml`.
2. If you cloned a repository for deployment, update it with `git pull`.
3. Remove old images to free space (optional, use with caution):

```bash
docker system prune -a
```

Warning: this command removes all Docker images on your computer. If you use Docker for other projects, remove images selectively using `docker rmi`.

## Related Pages

- [MongoDB Local Installation Guide](mongodb_installation.md)
- [Web Services Usage Guide](web_services_usage.md)
- [Database Dumps](../database_dumps.md)

## Last Review

- Last updated: 2026-02-10
- Responsible area: RegulonDB Documentation and Governance Team
