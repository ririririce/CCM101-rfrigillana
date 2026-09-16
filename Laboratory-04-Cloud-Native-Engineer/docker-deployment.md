# Docker Container Lifecycle

## 1. List Running Containers

```bash
docker ps
```

This command lists all containers that are currently running.

## 2. Stop the Running Container

```bash
docker stop nginx-server
```

This command stops the running Nginx container named `nginx-server`.

## 3. Verify the Container Is Stopped

```bash
docker ps
```

This command checks the running containers and confirms that `nginx-server` is no longer running.

## 4. Remove the Container Completely

```bash
docker rm nginx-server
```

This command permanently removes the stopped `nginx-server` container from the Docker environment.
