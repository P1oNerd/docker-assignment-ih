# Use official Node.js LTS image as base
FROM node:18-alpine

# Set the working directory inside the container
WORKDIR /app

# Copy package.json first (so Docker caches npm install separately)
COPY package*.json ./

# Install dependencies
RUN npm install --production

# Copy the rest of the backend source code
COPY . .

# The backend listens on port 3001 (from the README)
EXPOSE 3001

# Command to start the server
CMD ["node", "server.js"]
