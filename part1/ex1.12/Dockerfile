# Use an official Node.js runtime as a parent image
FROM node:16-alpine

# Set the working directory in the container
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install the project dependencies
RUN npm install

# Copy the rest of the application files to the working directory
COPY . .

# Build the project
RUN npm run build

# Install 'serve' to serve the static files
RUN npm install -g serve

# Expose port 5000 to the host
EXPOSE 5000

# Command to run the application
CMD ["serve", "-s", "-l", "5000", "build"]
