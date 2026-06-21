FROM openjdk:17-alpine
WORKDIR /app
COPY . .
RUN ./mvnw clean package
EXPOSE 8080
CMD ["java", "-jar", "target/voting-0.0.1-SNAPSHOT.jar"]