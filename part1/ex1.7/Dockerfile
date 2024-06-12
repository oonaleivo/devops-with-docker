# Start from the ubuntu:22.04 image
FROM ubuntu:22.04

# Update the package list and install curl
RUN apt-get update && apt-get install -y curl

# Set the working directory
WORKDIR /usr/src/app

# Copy the script into the image
COPY script.sh .

# Set the command to run the script
CMD ["./script.sh"]
