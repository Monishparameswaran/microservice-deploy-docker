FROM maven as monishbuild
WORKDIR /app
COPY . .
RUN mvn install

FROM openjdk:11.0.10-jre
WORKDIR /app
COPY --from=monishbuild /app/target/zuul-0.0.1-SNAPSHOT.jre .
CMD ["java","-jar","zuul-0.0.1-SNAPSHOT.jar"]