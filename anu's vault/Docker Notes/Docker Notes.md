
**Docker Notes**

## What is Docker?

Docker is an open-source platform that enables developers to build, package, and distribute applications in lightweight, portable containers. It simplifies application deployment by providing a consistent runtime environment across different computing environments. Docker eliminates issues related to "it works on my machine" by ensuring applications run the same regardless of where they are deployed.

## What is Containerization?

Containerization is a lightweight virtualization technology that packages an application and its dependencies into a container. Unlike virtual machines (VMs), which include a full operating system, containers share the host OS kernel while maintaining isolation. This makes containers more efficient, faster, and easier to deploy and manage compared to traditional VMs.

## Basic Docker Commands

### 1. Check Running Containers

```bash
docker ps
```

**Options:**

- `-a` : Show all containers, including stopped ones.
- `-q` : Show only container IDs.
- `--format "{{.Names}}"` : Display container names.

**Example:**

```bash
docker ps -a
```

### 2. Run a Container

```bash
docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
```

**Options:**

- `-d` : Run container in detached mode (background).
- `-it` : Run interactively with a terminal.
- `--name` : Assign a name to the container.
- `-p HOST_PORT:CONTAINER_PORT` : Map container ports to the host.
- `--rm` : Automatically remove the container after it exits.

**Example:**

```bash
docker run -it --rm ubuntu bash
```

(Runs an interactive Ubuntu container that removes itself after exiting.)

### 3. Stop a Running Container

```bash
docker stop CONTAINER_ID
```

**Example:**

```bash
docker stop my_container
```

### 4. Remove a Container

```bash
docker rm CONTAINER_ID
```

**Example:**

```bash
docker rm my_container
```

### 5. List Docker Images

```bash
docker images
```

**Options:**

- `-q` : Show only image IDs.
- `--format "{{.Repository}}:{{.Tag}}"` : Display image names and tags.

**Example:**

```bash
docker images -q
```

### 6. Pull an Image from Docker Hub

```bash
docker pull IMAGE_NAME
```

**Example:**

```bash
docker pull nginx
```

### 7. Remove an Image

```bash
docker rmi IMAGE_ID
```

**Example:**

```bash
docker rmi nginx
```

### 8. View Container Logs

```bash
docker logs CONTAINER_ID
```

**Options:**

- `-f` : Follow real-time logs.
- `--tail N` : Show last N lines.

**Example:**

```bash
docker logs -f my_container
```

### 9. Execute a Command in a Running Container

```bash
docker exec [OPTIONS] CONTAINER COMMAND [ARG...]
```

**Options:**

- `-it` : Run interactively with a terminal.

**Example:**

```bash
docker exec -it my_container bash
```

### 10. Remove All Stopped Containers

```bash
docker container prune
```

These commands help manage Docker containers and images efficiently.