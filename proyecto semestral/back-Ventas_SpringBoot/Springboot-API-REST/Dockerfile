# Etapa 1: Compilación de la aplicación
FROM maven:3.8.8-eclipse-temurin-17 AS build
WORKDIR /app
# Copiamos el archivo de configuración de Maven y el código fuente
COPY pom.xml .
COPY src ./src
# Compilamos saltándonos los tests para agilizar el pipeline
RUN mvn clean package -DskipTests

# Etapa 2: Imagen de ejecución ligera
FROM eclipse-temurin:17-jre-alpine
WORKDIR /app
# Copiamos el JAR generado en la etapa anterior
COPY --from=build /app/target/*.jar app.jar
# Exponemos el puerto interno por defecto de Spring Boot
EXPOSE 8080
# Comando para ejecutar la API
ENTRYPOINT ["java", "-jar", "app.jar"]