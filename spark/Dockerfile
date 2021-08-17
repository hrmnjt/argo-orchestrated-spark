FROM hseeberger/scala-sbt:8u242_1.3.8_2.13.1 as builder

WORKDIR /app/src/

COPY . .
RUN sbt clean && sbt assembly
RUN ls -al /app/src/target/

FROM openjdk:8-jre

COPY --from=builder /app/src/target/scala-2.13/hello-world-assembly-1.0.jar /app/hello-world-assembly-1.0.jar

ENTRYPOINT ["java", "-jar", "\/app\/hello-world-assembly-1.0.jar"]