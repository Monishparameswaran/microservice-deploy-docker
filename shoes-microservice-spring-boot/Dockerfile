FROM maven as monishbuild
WORKDIR /app
COPY . .
RUN mvn install

FROM openjdk:11.0.10-jre
WORKDIR /app
COPY --from=monishbuild /app/target/shoes-0.0.1-SNAPSHOT.jar .
EXPOSE 1002
CMD ["java","-jar","shoes-0.0.1-SNAPSHOT.jar"]