FROM maven:3.9-eclipse-temurin-17 AS builder

WORKDIR /demo/app

COPY /demo .

RUN mvn clean package -DskipTests



FROM eclipse-temurin:17-jre

WORKDIR /app

COPY --from=builder /demo/app/target/*.jar app.jar

EXPOSE 8080

CMD ["java", "-jar", "app.jar"]