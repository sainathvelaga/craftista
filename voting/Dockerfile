FROM eclipse-temurin:17-jdk
WORKDIR /app
COPY . .
RUN mvn clean install
EXPOSE 8080
CMD ["java", "-jar", "target/voting-0.0.1-SNAPSHOT.jar"]