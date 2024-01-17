FROM maven:3.8.4-openjdk-17-slim AS builder
WORKDIR /app

COPY pom.xml .
COPY src src

RUN mvn clean package -DskipTests

FROM amazoncorretto:17.0.7-alpine AS final
WORKDIR /app
COPY --from=builder /app/target/*.jar /app/app.jar

EXPOSE 8080
CMD ["java", "-jar", "app.jar"]
