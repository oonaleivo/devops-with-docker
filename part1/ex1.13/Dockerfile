# Use an official Golang runtime as a parent image
FROM golang:1.16-alpine

# Set the working directory inside the container
WORKDIR /app

# Copy go.mod and go.sum files
COPY go.mod go.sum ./

# Download all dependencies
RUN go mod download

# Copy the rest of the application files
COPY . .

# Build the application
RUN go build -o server .

# Expose port 8080 to the host
EXPOSE 8080

# Set environment variable for the port
ENV PORT=8080

# Command to run the application
CMD ["./server"]
