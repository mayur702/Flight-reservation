FROM openjdk:17-jdk-slim
WORKDIR /app

COPY target/flightreservationApplication-0.0.1-SNAPSHOT.jar app.jar

EXPOSE 8080

HEALTHCHECK --interval=30s --timeout=10s --retries=3 CMD curl -f http://18.117.145.160:8080/actuator/health || exit 1

ENTRYPOINT ["java", "-jar", "app.jar"]

