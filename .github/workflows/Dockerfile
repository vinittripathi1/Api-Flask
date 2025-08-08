# Use a Node.js base image
FROM node:lts-alpine

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json to the container
# This allows npm ci to use the cached layers if these files haven't changed
COPY package.json package-lock.json ./

# Run npm ci to install dependencies
RUN npm ci

# Copy the rest of the application code
COPY . .

# Expose the port your application listens on (if applicable)
EXPOSE 3000

# Define the command to run your application
CMD ["npm", "start"]
