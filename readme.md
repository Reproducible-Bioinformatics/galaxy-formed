# Galaxy Formed

Galaxy Formed is a Docker Compose setup to run a customized Galaxy instance
with additional tools.

## Overview

This setup includes:
- **Galaxy**: A bioinformatics platform for data analysis.
- **Lemaitre**: A tool container for managing personal tools within Galaxy.

### Services

- **lemaitre**:
  - Exposes port `8081`.

- **galaxy**: Runs the `quay.io/bgruening/galaxy` image.
  - Exposes multiple ports:
    - `8080` → Galaxy Web UI.
    - `8021` → FTP service.
    - `8022` → SSH service.
  - Uses a shared volume for persistent storage and tool management.
  - Configures additional tool configurations.

## Usage

1. Clone the repository:
   ```sh
   git clone https://github.com/Reproducible-Bioinformatics/galaxy-formed.git
   cd galaxy-formed
   ```
2. Start the services:
   ```sh
   docker-compose up -d
   ```
3. Access the Galaxy instance at
   [http://localhost:8080](http://localhost:8080).

## Stopping and Cleaning Up

To stop the containers:
```sh
docker-compose down
```

To remove volumes (warning: this will delete stored data):
```sh
docker-compose down -v
```
