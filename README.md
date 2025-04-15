# UCS Superset Docker Setup
This repository provides a Docker-based setup for running Apache Superset, configured to connect to a PostgreSQL server running on the host machine.

## Prerequisites

- Docker and Docker Compose installed
- PostgreSQL server installed and running as a service on the host machine

## Setup Instructions

1. **Clone the Superset repository** (if not already):
   ```bash
   git clone https://github.com/apache/superset.git
   cd superset
   ```

2. **Replace the default `docker-compose.yml`** with the one from this repository:
   ```bash
   cp /path/to/ucs-docker-superset/docker-compose.yml ./docker-compose.yml
   ```

3. **Copy the `.env-local` file** into the `docker` directory of the Superset repository:
   ```bash
   cp /path/to/ucs-docker-superset/.env-local ./docker/.env-local
   ```

4. **Start Superset**:
   ```bash
   docker compose up
   ```

Superset will be available at [http://localhost:8088](http://localhost:8088).

## Notes

- The setup uses `host.docker.internal` to connect to the host machine’s PostgreSQL server. Ensure your PostgreSQL server is configured to accept external connections and that the credentials match those in `.env-local`.
- Make sure ports `8088` and `5432` are available on your system.
