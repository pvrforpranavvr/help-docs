# 📝 Setup MinIO Locally

## 1. Using Docker

To set up MinIO on your local machine using Docker, run the following command:

```bash
docker run -p 9000:9000 -p 9001:9001 \
  -e MINIO_ROOT_USER=minioadmin \
  -e MINIO_ROOT_PASSWORD=minioadmin \
  quay.io/minio/minio server /data --console-address ":9001"
```
This will start MinIO with the following ports:

9000: For the MinIO API (S3-compatible).

9001: For the MinIO web console.

## 2. Access the Web Console

  http://localhost:9001/

### Default Credentials:

Username: minioadmin

Password: minioadmin

## To get local ip of mac

    ipconfig getifaddr en0
