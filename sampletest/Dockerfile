# ---------- Stage 1: Build ----------
FROM maven:3.8.3-openjdk-17 AS build
COPY . .

RUN mvn clean install 

# ---------- Stage 2: Run ----------
FROM ecplise-temurin:17-jdk-alpine

COPY --from=build /app/target/sampletest-0.0.1-SNAPSHOT.jar sampletest.jar

EXPOSE 8081

ENTRYPOINT ["java", "-jar", "sampletest.jar"]