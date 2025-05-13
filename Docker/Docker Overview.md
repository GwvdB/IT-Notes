Docker is an open-source platform for building, shipping, and running applications in isolated environments called **containers**. Containers package applications with all their dependencies, allowing them to run consistently across different environments.

## Topics

- [[Docker Overview#What is Docker|What is Docker]]
- [[Docker Overview#Virtual Machine vs Container|Virtual Machine vs Container]]
- [[Docker Overview#Docker Architecture|Docker Architecture]]
- [[Docker Overview#Installing Docker|Installing Docker]]
- [[Docker Commands]]
- [[Creating an Image]]
- [[Docker Overview#Docker in Action|Docker in Action]]

---

# What is Docker

[[Docker Overview]]

Docker enables applications to be packaged in **containers**—lightweight, portable units that run consistently across diverse environments. Docker’s portability helps solve issues related to dependency conflicts and differences in OS environments.

For more on the difference between containers and virtual machines, see [[#Virtual Machine vs Container]].

---

# Virtual Machine vs Container

[[Docker Overview]]

|Feature|Virtual Machine|Container|
|---|---|---|
|**Isolation**|Full OS instance per VM|Lightweight, shares OS kernel with host|
|**Performance**|Moderate to heavy resource usage|Highly efficient, minimal overhead|
|**Boot Time**|Longer, often several minutes|Quick, typically in seconds|
|**Size**|Large, includes entire OS|Small, shares host OS, only app and dependencies|
|**Scalability**|Limited by the need for full OS instances|Scales easily due to low overhead|

Containers are lightweight and designed for efficient scalability, making them ideal for modern cloud-based and microservices architectures. For a deeper understanding of Docker’s structure, see [[#Docker Architecture]].

---

# Docker Architecture

[[Docker Overview]]

Docker operates on a client-server architecture, comprising:

- **Docker Client**: Accepts commands and communicates with the Docker Daemon.
- **Docker Daemon**: The core service that builds, runs, and manages containers.
- **Docker Images**: Templates used to create containers.
- **Docker Containers**: Isolated environments created from images.
- **Docker Registry**: A repository for storing and retrieving Docker images, like Docker Hub.

For instructions on installing Docker, go to [[#Installing Docker]].

---

# Installing Docker

[[Docker Overview]]

### Installing Docker Desktop for Windows & macOS

1. Download Docker Desktop from Docker’s official website.
2. Run the installer and follow the setup steps.

### Installing Docker Engine on Linux

1. **Update package index**:
```
sudo apt-get update
```

2. Install prerequisites:
```
sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
```

3. Add Docker's GPG key and set up repository:
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

4. Install Docker:
```
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

Once installed, start exploring Docker with [[Docker Commands]] and learn to build images with [[Creating an Image]].

---

# Docker in Action

[[Docker Overview]]

Once Docker is installed, start using it with commands to pull images, create and manage containers, and monitor their behavior.

### a. Pulling an Image

```
docker pull <image_name>
```

Example: `docker pull nginx` pulls the official NGINX image.

### b. Running a Container

```
docker run -d -p 80:80 nginx
```

This command runs NGINX in detached mode on port 80.

### c. Building and Running Custom Images

For custom builds, see the steps in [[Creating an Image]].

### d. Docker Compose for Multi-Container Apps

Docker Compose allows you to define and manage multi-container applications with a `docker-compose.yml` file.

```
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

```
docker-compose up
```

For further command references, see [[Docker Commands]].