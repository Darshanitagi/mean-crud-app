# Stage 1: Build the optimized production image
FROM node:18-alpine

# Create app directory
WORKDIR /usr/src/app

# Copy package.json and package-lock.json to install dependencies
COPY package*.json ./

# Install application dependencies
RUN npm install

# Copy application source code
COPY . .

# Expose the port the application runs on
EXPOSE 3000

# Start the application
CMD [ "node", "server.js" ]