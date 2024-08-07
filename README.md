# Docker Compose Project

## Overview

This project uses Docker Compose to manage multiple services with configurations for different environments (PROD, DEV, TEST). The setup includes Go code to generate Docker Compose files for each environment.

## Folder Structure

- `services/` - Contains separate Docker Compose service files.
- `generate-compose.go` - Go program to generate Docker Compose file. Will be generated in compose folder
- `compose/` folder will also contain ___.env___ & volumes associated with different services once we start our services
- Different level of permission might be needed for volumes associted with different services

## Generating Docker Compose File & Start Docker services

- Run the Go program to generate Docker Compose files for all environments: `go run generate-compose.go` or `./generate-compose`
- Now from inside `compose` run `docker compose up -d`