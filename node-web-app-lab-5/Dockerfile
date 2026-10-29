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
