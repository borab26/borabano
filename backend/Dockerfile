FROM maven:3.6.3-openjdk-11 AS maven_build
COPY pom.xml /tmp/
COPY src /tmp/src/
WORKDIR /tmp/
RUN mvn package

FROM openjdk
MAINTAINER borabano4@gmail.com
EXPOSE 8080
CMD java -jar /data/quiz-0.0.1-SNAPSHOT.jar
COPY --from=maven_build /tmp/target/quiz-0.0.1-SNAPSHOT.jar /data/quiz-0.0.1-SNAPSHOT.jar
