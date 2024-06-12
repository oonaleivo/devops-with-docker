# Use Amazon Corretto 8 as the base image
FROM amazoncorretto:8

# Set the working directory inside the container
WORKDIR /app

# Install dos2unix to convert line endings
RUN yum install -y dos2unix

# Copy the Maven wrapper and the .mvn directory
COPY .mvn .mvn
COPY ./mvnw ./mvnw
COPY ./pom.xml ./pom.xml

# Copy the source code
COPY ./src ./src

# Convert line endings of the Maven wrapper script
RUN dos2unix ./mvnw

# Make the Maven wrapper executable
RUN chmod +x ./mvnw

# Build the application
RUN ./mvnw package

# Expose port 8080
EXPOSE 8080

# Run the application
CMD ["java", "-jar", "./target/docker-example-1.1.3.jar"]
