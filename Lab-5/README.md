# Lab 5: Node.js Web App Pushed to Docker Hub

**Goal:** Containerize a Node.js app and push the image to Docker Hub.

You need a Docker Hub account. Sign up at https://hub.docker.com if you don't have one.

## Step 1: Create the project folder

```bash
cd ~/Downloads/devops-practice
mkdir node-web-app
cd node-web-app
```

## Step 2: Create `package.json`

Create a file named `package.json`:

```json
{
  "name": "node-web-app",
  "version": "1.0.0",
  "description": "A simple Node.js web app for Docker",
  "main": "server.js",
  "scripts": {
    "start": "node server.js"
  },
  "dependencies": {}
}
```

This app uses only Node's built-in modules, so there are no dependencies to install.

## Step 3: Create `server.js`

Create a file named `server.js`:

```javascript
const http = require('http');

const PORT = 8080;

const server = http.createServer((req, res) => {
  res.writeHead(200, { 'Content-Type': 'text/html' });
  res.end(`
    <!DOCTYPE html>
    <html>
    <head><title>Node Web App</title></head>
    <body>
      <h1>Hello from my Node.js app in Docker!</h1>
      <p>Served from port ${PORT} inside the container.</p>
    </body>
    </html>
  `);
});

server.listen(PORT, () => {
  console.log(`Server running on port ${PORT}`);
});
```

The app listens on port 8080 inside the container. The lab maps host port 49160 to that port.

## Step 4: Create the `Dockerfile`

Create a file named exactly `Dockerfile` (no extension):

```dockerfile
# Use the official Node.js image (Alpine is small)
FROM node:20-alpine

# Set the working directory inside the container
WORKDIR /usr/src/app

# Copy package.json first (takes advantage of layer caching)
COPY package*.json ./

# Install dependencies (none here, but this is the standard pattern)
RUN npm install

# Copy the rest of the application code
COPY . .

# The app listens on port 8080
EXPOSE 8080

# Start the app
CMD ["npm", "start"]
```

Your folder should look like this:

```
node-web-app/
├── Dockerfile
├── package.json
└── server.js
```

## Step 5: Build the image

```bash
docker build -t <DOCKERHUB_USER>/node-web-app .
docker images
```

Example: if your username is `saeed-asif`, the command is `docker build -t saeed-asif/node-web-app .`

If you already built the image under another name, add the Docker Hub name with a tag instead:

```bash
docker tag node-web-app <DOCKERHUB_USER>/node-web-app
```

## Step 6: Run the container

```bash
docker run -p 49160:8080 -d <DOCKERHUB_USER>/node-web-app
docker ps
```

Open **http://localhost:49160** in a browser. You should see "Hello from my Node.js app in Docker!"

## Step 7: Log in to Docker Hub

```bash
docker login
```

Enter your Docker Hub username and password, or a personal access token (more secure). You should see "Login Succeeded."

## Step 8: Push the image

```bash
docker push <DOCKERHUB_USER>/node-web-app
```

When the push finishes, the image is available at `https://hub.docker.com/r/<DOCKERHUB_USER>/node-web-app`.

## Troubleshooting

- **`denied: requested access to the resource is denied` when pushing:** The image name doesn't start with your Docker Hub username. Rebuild with the `<DOCKERHUB_USER>/` prefix, or run `docker tag`.
- **`unauthorized: authentication required`:** Run `docker login` again.
- **Port 49160 already in use:** Use another host port, such as `-p 49161:8080`.
- **Browser shows old content after code changes:** Rebuild the image, then stop and remove the old container before running the new one.

## Cleanup

```bash
docker ps                     # find the container ID
docker stop <container_id>
docker rm <container_id>
```
