[[Docker Overview]]

Docker images are templates used to create containers, including the application code and dependencies. You can create images using **Dockerfiles** or by **committing changes** to a running container.

## 1. Building an Image from a Dockerfile
A **Dockerfile** is a text file with instructions to assemble an image. Below is an example Dockerfile for a Node.js application.

#### Sample Dockerfile
```Dockerfile
# Use a base image
FROM node:14

# Set the working directory
WORKDIR /app

# Copy package files and install dependencies
COPY package*.json ./
RUN npm install

# Copy application code
COPY . .

# Expose the app port
EXPOSE 3000

# Run the app
CMD ["npm", "start"]
```

### Building an Image from a Dockerfile
To build an image, navigate to the Dockerfile directory and run:
```bash
docker build -t <image_name>:<tag> .
```

Example:
```bash
docker build -t mynodeapp:latest .
```

For managing your containers and images, refer to [[Docker Commands]].

## 2. Creating an Image from a Running Container
1. Start a container and make necessary changes.
2. Commit the container to an image:
   ```bash
   docker commit <container_id> <new_image_name>:<tag>
   ```

Explore more Docker actions like starting, stopping, and managing containers in [[Docker in Action]].

---

# Docker in Action
[[Docker Overview]]

Once Docker is installed, start using it with commands to pull images, create and manage containers, and monitor their behavior.

### a. Pulling an Image
```bash
docker pull <image_name>
```
Example: `docker pull nginx` pulls the official NGINX image.

### b. Running a Container
```bash
docker run -d -p 80:80 nginx
```
This command runs NGINX in detached mode on port 80.

### c. Building and Running Custom Images
For custom builds, see the steps in [[Creating an Image]].

### d. Docker Compose for Multi-Container Apps
Docker Compose allows you to define and manage multi-container applications with a `docker-compose.yml` file.

```yaml
version: '3'
services:
  web:
    image: nginx
    ports:
      - "80:80"
  db:
    image: mysql
    environment:
      MYSQL_ROOT_PASSWORD: examplepassword
```

To start the services:
```bash
docker-compose up
```

For further command references, see [[Docker Commands]].