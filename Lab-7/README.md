# Lab 7: Sharing Data Between Containers with volumes-from

This lab shows how two containers can share a volume. A file created in one container becomes visible in the other.

## Files

- `Dockerfile`: builds an Ubuntu image that declares `/myvolume1` as a volume

## Dockerfile

```dockerfile
FROM ubuntu:22.04
VOLUME /myvolume1
```

## Build and run

```bash
docker build -t myimage .

# Container1 creates the volume
docker run -it --name Container1 myimage /bin/bash
ls
exit

# Container2 shares Container1's volumes
docker run -it --name Container2 --volumes-from Container1 ubuntu /bin/bash
touch /myvolume1/testfile
exit

# Check from Container1
docker start Container1
docker attach Container1
ls /myvolume1
```

To detach from `Container1` without stopping it, press `Ctrl+P` then `Ctrl+Q`.

## Cleanup

```bash
docker rm Container1 Container2
docker rmi myimage
docker volume prune
```
