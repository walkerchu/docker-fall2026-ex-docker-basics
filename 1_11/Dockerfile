# DevOps with Docker, Fall 2026
# offer by The University of Helsinki
# Chapter 2/utilizing-tools-from-the-registry
# url: https://courses.mooc.fi/org/uh-cs/courses/devops-with-docker-fall-2026/chapter-2/utilizing-tools-from-the-registry
# Exercise 1.11. Spring
# created at Oct 17, 2026 14:34 HKT

FROM amazoncorretto:8

WORKDIR /app

# Copy the Maven wrapper files into the container
COPY .mvn/ .mvn
COPY mvnw .
COPY pom.xml .

# Download the dependencies (necessary for faster builds in the future)
RUN ./mvnw dependency:go-offline -B

# Copy the source code into the container
COPY src ./src

RUN ./mvnw package

CMD [ "java", "-jar", "./target/docker-example-1.1.3.jar" ]
 
