1. Create a build stage using an official Maven image i.e. `maven:3.9.6-eclipse-temurin-21-jammy` using `AS build` alias
1. Copy sources from `multi-stage-build` into your container
1. Use maven to build our app with `maven clean package`
1. Copy build artifact to the runtime image running an official jdk/jre image i.e. eclipse-temurin:21-jre-jammy
`COPY --from=build /source/target/hello-world-0.0.1-SNAPSHOT.jar /app/hello-world.jar`
1. Run application using `CMD ["java","-jar","/app/hello-world.jar"]`
1. Build the container with
```
docker build -t iteratec.io/multistage-build .
```
3. Inspect final image sizes.
4. Run the container
```
docker run -p 8080:8080 -d iteratec.io/multistage-build
```
5. Check whether application is running
```
curl 'http://localhost:8080'
Greetings from Spring Boot!%
```