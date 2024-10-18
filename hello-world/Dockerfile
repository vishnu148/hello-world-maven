FROM maven:3.6.3-jdk-8 AS build

WORKDIR /App
COPY . .
RUN mvn clean package

FROM openjdk:8-jre
WORKDIR /App
COPY --from=build /App/target/hello-world-1.0-SNAPSHOT.jar /App/hello-world.jar

ENTRYPOINT ["java", "-jar", "/App/hello-world.jar"]
