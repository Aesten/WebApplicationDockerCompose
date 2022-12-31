FROM gradle:jdk17 as GradleBuilder
COPY --chown=gradle:gradle . /home/gradle/src
WORKDIR /home/gradle/src
RUN gradle clean build -x test

FROM openjdk:17-jdk-slim as SpringApp
ENTRYPOINT ["sudo", "mkdir", "/app/"]
WORKDIR /app
ARG JAR_FILE=/home/gradle/src/build/libs/*.jar
COPY --from=GradleBuilder ${JAR_FILE} /app/app.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "/app/app.jar"]