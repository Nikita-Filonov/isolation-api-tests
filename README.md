# Isolation API Tests

A educational project that demonstrates a **banking system built with a microservice architecture,**
asynchronous operation processing, and an API Gateway for external integrations.

The main goal of the project is to showcase:

- microservice-based design;
- HTTP & gRPC APIs;
- asynchronous processing with Kafka;
- clean separation of domains;
- Docker-based local infrastructure.

## Project Overview

The system simulates basic banking flows such as creating and processing financial operations.

It consists of **two core domains:**

- Gateway Service — a single entry point for external clients.
- Operations Service — asynchronous processing of banking operations.

Additional services (`users`, `cards`, `accounts`) are used as example downstream services behind the gateway.

## Architecture

### High-Level Architecture

![High-Level Architecture](./docs/architecture/core.png)

### Gateway Service

![Gateway Service](./docs/architecture/gateway.png)

### Operations Service

![Operations Service](./docs/architecture/operations.png)

## Tech Stack

- Python 3.12
- FastAPI (HTTP)
- gRPC
- Kafka
- PostgreSQL
- SQLAlchemy (async)
- Alembic
- Docker / Docker Compose

## Setup & Run

### Prerequisites

- Docker
- Docker Compose

### Build base image

```shell
docker build -t base-service .
```

### Run services

```shell
docker-compose up -d
```

## Available services

- Gateway HTTP: http://localhost:8001
- Gateway gRPC: localhost:9001
- Operations HTTP: http://localhost:8002
- Operations gRPC: localhost:9002
- Kafka UI: http://localhost:8081
- pgAdmin: http://localhost:5050