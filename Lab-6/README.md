# L\ab 6: Custom Docker Image with Files and Environment Variables

This lab builds a custom Docker image from an Ubuntu base image. The image includes two test files and an environment variable. It then runs a container from the image and checks both from inside.

## Files

- `Dockerfile`: defines the image
- `testfile1`, `testfile2`: sample files copied into `/data` in the image

## Dockerfile

```dockerfile
FROM ubuntu:22.04
ENV myname=Saeed
COPY testfile1 testfile2 /data/
```

## Build and run

```bash
docker build -t newimage .
docker images
docker run -it --name ubuntucont newimage /bin/bash
```

Inside the container:

```bash
ls /data
echo $myname
exit
```

## Cleanup

```bash
docker rm ubuntucont
docker rmi newimage
```
