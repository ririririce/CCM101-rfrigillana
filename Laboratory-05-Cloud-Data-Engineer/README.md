# MinIO Deployment Documentation

## 1. Overview

In this activity, I used Docker to run a MinIO server in the KillerCoda Ubuntu playground. MinIO is an object storage service that allows users to store files such as images and videos. After setting it up, I accessed its web console, created a bucket, and uploaded a sample image.

## 2. Docker Commands Used

I used the following command to download and start the MinIO container:

```bash
docker run -d -p 9000:9000 -p 9001:9001 --name minio-server \
  -e "MINIO_ROOT_USER=cloudadmin" \
  -e "MINIO_ROOT_PASSWORD=CloudNova2026!" \
  ghcr.io/imagegenius/minio:latest
```

After running the command, I used `docker ps` to check if the container was running.

```bash
docker ps
```

The output showed that my `minio-server` container was running, which meant that the deployment was successful.

## 3. Port Configuration

I used two ports for the MinIO server:

| Port | Purpose |
|---|---|
| 9000 | Used for the MinIO API to communicate with applications. |
| 9001 | Used to open the MinIO Web Console in a browser. |

I accessed the web console through KillerCoda's port-forwarding feature using port 9001.

## 4. Environment Variables

The `-e` flags in the Docker command were used to set the login credentials for MinIO.

- `MINIO_ROOT_USER=cloudadmin` sets the administrator username.
- `MINIO_ROOT_PASSWORD=CloudNova2026!` sets the administrator password.

I used these credentials to log in to the MinIO Web Console.

## 5. Bucket Creation and File Upload

After logging in, I created a bucket named `client-photos`. I then uploaded a sample image called `cel.jpg`. The image appeared in the bucket after the upload, showing that I was able to store a file successfully.

## 6. Conclusion

Through this activity, I learned how to run a storage server using Docker and access it through a web browser. I also learned how to check running containers, configure ports, and set environment variables. Creating the bucket and uploading an image helped me understand how object storage works in practice.
