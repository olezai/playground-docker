# Using an official Ubuntu 22.04 image
FROM ubuntu:22.04

# Install necessary dependencies and JDK 8
RUN apt-get update && \ 
	apt-get install -y wget curl gnupg openjdk-8-jdk && \
	apt-get clean

WORKDIR /app

COPY src/* .

RUN javac HelloWorld.java

CMD ["java", "HelloWorld"]