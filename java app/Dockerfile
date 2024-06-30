#  FROM almalinux

# RUN  yum update -y &&  yum install java-11-openjdk -y &&  yum install git -y &&  yum install maven -y

# RUN git clone https://github.com/up1/maven_java_web_example.git

# WORKDIR $PWD/maven_java_web_example

# RUN mvn clean

# RUN mvn test -X

# RUN mvn package

# CMD ["mvn" , "tomcat7:run"]

# Use the official OpenJDK 17 image as the base image
FROM openjdk:17-jdk-alpine

# Set the maintainer label
LABEL maintainer="baeldung.com"

# Set the working directory inside the container
WORKDIR $PWD/maven_java_web_example

RUN mvn clean

RUN mvn test -X

RUN mvn package

# Copy the generated jar (replace 'docker-java-jar-0.0.1-SNAPSHOT.jar' with your actual jar name)
COPY target/docker-java-jar-0.0.1-SNAPSHOT.jar app.jar

# Specify the entry point for the container
ENTRYPOINT ["java", "-jar", "/app.jar"]
