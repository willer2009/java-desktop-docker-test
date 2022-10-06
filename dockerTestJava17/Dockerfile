# Build a JAR File
FROM maven:3.8.3-openjdk-17 AS build
WORKDIR /app
COPY . /app

run mvn -f /app/pom.xml clean package

# create an Image
FROM khipu/openjdk17-alpine
EXPOSE 5001
COPY --from=build /app/target/Test-1.0-SNAPSHOT.jar Test.jar
ENTRYPOINT ["sh", "-c", "java -jar /Test.jar"]