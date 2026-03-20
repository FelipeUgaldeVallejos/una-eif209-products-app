FROM maven:4.0.0-rc-4-eclipse-temurin-25 AS build


WORKDIR /app

COPY pom.xml .
COPY src ./src

RUN mvn  package -DskipTests

from eclipse-temurin:25

WORKDIR /app

COPY --from=build /app/target/*.jar app.jar

CMD ["java", "-jar", "app.jar"]