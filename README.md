# foodchain-config

Central **YAML configuration** for FoodChain microservices consumed by **Spring Cloud Config Server**. Each file usually matches `spring.application.name` (for example `order-service.yml`, `api-gateway.yml`).

## Usage

- Mounted read-only into the config-server container in **foodchain-deployment** (`/config-repo`).
- Defines cross-cutting settings: **`server.port`**, datasource URLs, **`jwt.secret`**, Kafka bootstrap servers, Eureka zone URL, and service-specific topic names.

## Editing

Change values here when you want **all** instances that load config server (Compose, shared dev cluster) to pick up new defaults. Keep secrets out of Git where possible — prefer environment variables referenced from YAML (`${JWT_SECRET}`).

## Related

Run **config-server** on port **8888** and point services at `http://localhost:8888` (or `http://config-server:8888` inside Docker network).
