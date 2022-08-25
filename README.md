# Docker Compose Project

1. [Features](#features)
2. [Folder structure](#folder-structure)
3. [Example services](#example-services)
4. [Documentation](#documentation)
5. [TODO](#todo)

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