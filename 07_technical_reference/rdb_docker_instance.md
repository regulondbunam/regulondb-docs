# How to Install a Local Instance of RegulonDB

This guide explains how to run a complete local instance of RegulonDB (database, web application, and GraphQL API) with Docker.

## Required Software

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Installation Guide

1. Download or copy the content of the [Docker configuration file](https://regulondbdata.ccg.unam.mx/docker/docker-compose.yml) and save it as `docker-compose.yml`.
2. In a terminal, go to the folder where `docker-compose.yml` is located.
3. Get the required images from Docker Hub:

```bash
docker compose pull
```

4. When the download is completed, start the RegulonDB instance:

```bash
docker compose up -d
```

## Access Endpoints

Your instance is now available at:

- Web application: [http://localhost:7000/](http://localhost:7000/)
- GraphQL Playground and API: [http://localhost:7000/graphql](http://localhost:7000/graphql)

To stop the instance, go to the folder of `docker-compose.yml` and run:

```bash
docker compose down
```

## New Releases

When a new version of RegulonDB is released:

1. Replace your `docker-compose.yml` with the new version of the file (or, if you cloned a repository for the deployment, update it with `git pull`).
2. Repeat the installation steps.
3. Optionally, free disk space by removing the images of the previous version:

```bash
docker system prune -a
```

**Warning:** this command removes **all** Docker images on your computer. If you use Docker for other projects, remove the old RegulonDB images one by one with `docker rmi`.

## Related Pages

- [Database Dumps](../02_data_access/database_dumps.md)
- [MongoDB Local Installation Guide](../02_data_access/technical_resources/mongodb_installation.md)
- [API Access (GraphQL)](../02_data_access/api_access.md)

## Last Review

- Last updated: 2026-11-18
- Responsible area: RegulonDB Documentation and Governance Team
