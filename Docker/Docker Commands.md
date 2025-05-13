[[Docker Overview]]

The following commands are essential for managing Docker containers, images, networks, and volumes.

## Basic Docker Commands

### 1. Docker Version and Info
- **Check Docker Version**:
  ```bash
  docker --version
  ```
- **Detailed Docker Info**:
  ```bash
  docker info
  ```

### 2. Managing Images
- **List Images**:
  ```bash
  docker images
  ```
- **Pull an Image from a Registry**:
  ```bash
  docker pull <image_name>
  ```
- **Remove an Image**:
  ```bash
  docker rmi <image_id or image_name>
  ```

### 3. Managing Containers
- **List Running Containers**:
  ```bash
  docker ps
  ```
- **Run a New Container**:
  ```bash
  docker run <options> <image_name>
  ```
  Example: `docker run -d -p 80:80 nginx` to run NGINX in detached mode on port 80.

- **Stop a Running Container**:
  ```bash
  docker stop <container_id>
  ```
- **Remove a Stopped Container**:
  ```bash
  docker rm <container_id>
  ```

For more on creating custom Docker images, see [[Creating an Image]].