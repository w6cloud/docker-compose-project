# Docker Compose Project

- [Docker Compose Project](#docker-compose-project)
    - [Features](#features)
    - [Folder structure](#folder-structure)
    - [Example services](#example-services)
    - [Documentation](#documentation)
    - [TODO](#todo)

This template helps managing complex docker compose base projects.

## Features

- Clear file organization
- Configuration via .env file
- Multiple docker-compose files
- Traefik routing
- Dev / Prod profiles
- Makefile

## Folder structure

```pre
┣ services                          # Services configuration
┃┣ docker-compose.yml               # Global configuration
┃┗ service_1                        # First service
┃  ┣ docker-compose.override.yml    # First service config
┃  ┗ ...                            # First service configuration files
┃┗ service_2
┃  ┣ docker-compose.override.yml
┃  ┗ ...
┣ src                               # Application code
┃┗ ...
┗ .env                              # Configuration
```

## Example services

The template is configured with 3 example services :

- php
- db
- pma

## Documentation

- [Services](services/README.md)

## TODO

- [ ] Logging
- [ ] Mail routing
- [ ] Docker Validation / Linting
- [ ] Script to automate string replacements