# Lab 8: Volume Sharing Between Containers Using -v and --volumes-from

This lab creates a volume in one container, adds files to it, and checks that a second container can see the same files.

## Steps

Create the first container with an anonymous volume at `/volume2`, then add files:

```bash
docker run -it --name container4 -v /volume2 ubuntu /bin/bash
cd /volume2
touch file1 file2
exit
```

Start a second container that shares the first container's volumes:

```bash
docker run -it --name Container5 --volumes-from container4 ubuntu /bin/bash
ls /volume2
```

You should see `file1` and `file2`.

## Cleanup

```bash
docker rm container4 Container5
docker volume prune
```
