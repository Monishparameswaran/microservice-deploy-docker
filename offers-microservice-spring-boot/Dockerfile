FROM maven as monishbuild
WORKDIR /app
COPY . .
RUN mvn install

FROM openjdk:11.0.10-jre
WORKDIR /app
COPY --from=monishbuild /app/target/offers-0.0.1-SNAPSHOT.jar .
EXPOSE 1001
CMD ["java","-jar","offers-0.0.1-SNAPSHOT.jar"]