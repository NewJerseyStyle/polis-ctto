# Use an official Node.js runtime as a parent image
FROM node:22-slim

# Set the working directory in the container
WORKDIR /app

# Copy only the necessary files to the container
COPY polis.client /app/polis.client

# Change directory to polis.client
WORKDIR /app/polis.client

# Install only production dependencies
RUN npm install --only=production

# Build the app for production
RUN npm run build

# Install a simple HTTP server to serve the static files
RUN npm install -g serve

# Make port 80 available to the world outside this container
EXPOSE 80

# Serve the built app
CMD ["serve", "-s", "build", "-l", "80"]
