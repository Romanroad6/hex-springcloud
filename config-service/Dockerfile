FROM anapsix/alpine-java:8_server-jre_unlimited
MAINTAINER codeyung(616724895@qq.com)
ADD ["target/config-service-0.0.1-SNAPSHOT.jar", "app.jar"]
EXPOSE 8030
ENV JAVA_OPTS="-Xdebug -Dspring.profiles.active=native -jar -Xmx64m -Xms64m"
RUN sh -c 'touch /app.jar'
HEALTHCHECK CMD curl -f http://localhost:8030/actuator/health || exit 1
ENTRYPOINT [ "sh", "-c", "java $JAVA_OPTS -jar /app.jar" ]