# Docker Compose Project

## Overview

This project uses Docker Compose to manage multiple services with configurations for different environments (PROD, DEV, TEST). The setup includes Go code to generate Docker Compose files for each environment.

## Folder Structure

- `services/` - Contains separate Docker Compose service files.
- if you don't want any service to add in final docker compose you can add ___`?`___ (eg: `?rabbitmq.yml`) prefix to the file name of that service.
- `generate-compose.go` - Go program to generate Docker Compose file. Will be generated in compose folder
- build it using the following command `go build -o generate-compose` & run `./generate-compose`
- `/.` root folder contains ___.env___ & 
- `volumes` folder contains volumes associated with different services once we start our services
- Different level of permission might be needed for volumes associted with different services

## Generating Docker Compose File & Start Docker services

- From root dir `./` Run the Go program to generate Docker Compose files: `go run generate-compose.go` or `./generate-compose`
- Now from root dir `./` run `docker compose up -d`