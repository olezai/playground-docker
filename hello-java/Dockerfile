# Use official OpenJDK 8 image
FROM openjdk:8

# Set working directory
WORKDIR /app

WORKDIR /app

# Copy the Java file into the container
COPY src/* .

# Compile the Java file
RUN javac HelloWorld.java

# Command to run the compiled class
CMD ["java", "HelloWorld"]