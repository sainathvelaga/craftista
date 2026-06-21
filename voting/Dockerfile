# Build stage: use an image with Maven to compile the project
FROM maven:3.9.4-eclipse-temurin-17 AS build
WORKDIR /app
COPY pom.xml mvnw ./
RUN mvn -B -ntp dependency:go-offline
COPY . .
RUN mvn -B clean package -DskipTests

# Runtime stage: use a lightweight JDK image to run the built jar
FROM eclipse-temurin:17-jdk
WORKDIR /app
COPY --from=build /app/target/voting-0.0.1-SNAPSHOT.jar /app/voting.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "/app/voting.jar"]