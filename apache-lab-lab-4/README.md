# Lab 4: Apache Web Server in a Custom Docker Image

**Goal:** Build an image from a Dockerfile and serve a web page through a port mapping.

## Step 1: Check that Docker is installed

```bash
docker --version
docker run hello-world
```

If `docker` is not found, install Docker Desktop (Windows/macOS) or Docker Engine (Linux) first.

## Step 2: Create the project folder

```bash
mkdir -p ~/Downloads/devops-practice/apache-lab
cd ~/Downloads/devops-practice/apache-lab
```

## Step 3: Create `index.html`

Create a file named `index.html` in the `apache-lab` folder:

```html
<!DOCTYPE html>
<html>
<head>
    <title>My Apache Server</title>
</head>
<body>
    <h1>Hello from my custom Apache Docker image!</h1>
    <p>This page is served by Apache running inside a container.</p>
</body>
</html>
```

## Step 4: Create the `Dockerfile`

Create a file named exactly `Dockerfile` (no extension) in the same folder:

```dockerfile
# Use the official Apache HTTP Server image as the base
FROM httpd:2.4

# Copy our web page into Apache's document root
COPY index.html /usr/local/apache2/htdocs/index.html
```

The `httpd:2.4` image already has Apache installed and listens on port 80. Its document root is `/usr/local/apache2/htdocs/`.

Your folder should look like this:

```
apache-lab/
├── Dockerfile
└── index.html
```

## Step 5: Build the image

```bash
docker build -t apacheserver .
docker images
```

- The `.` tells Docker to use the current folder as the build context.
- The `-t` flag gives the image a name.
- `docker images` should list `apacheserver`.

## Step 6: Run the container with a port mapping

Port 80 may already be in use on your machine (for example, by Nginx or Apache). Check with:

```bash
sudo ss -tlnp | grep :80
```

If port 80 is free, run:

```bash
docker run -d -p 80:80 --name apache apacheserver
```

If port 80 is in use, map a different host port to port 80 in the container:

```bash
docker run -d -p 8080:80 --name apache apacheserver
```

- `-d` runs the container in the background.
- `-p HOST:CONTAINER` maps a port on your computer to a port inside the container.

## Step 7: View the web page

Open a browser and go to:

- `http://localhost` (if you used port 80), or
- `http://localhost:8080` (if you used port 8080)

You should see "Hello from my custom Apache Docker image!"

You can also check from the terminal:

```bash
curl http://localhost:8080
```

Check that the container is running:

```bash
docker ps
```

## Troubleshooting

- **`address already in use` on port 80:** Another program holds port 80. Use `-p 8080:80` instead, or stop that program (for example `sudo systemctl stop nginx`). Remove the failed container first with `docker rm apache`.
- **`permission denied` on port 80 (Linux):** Use a higher port like 8080, or run with `sudo`.
- **Changes to `index.html` don't appear:** Rebuild the image with `docker build -t apacheserver .`, then stop and remove the old container and run a new one.

## Cleanup

```bash
docker ps                     # find the container ID or name
docker stop apache
docker rm apache
```
