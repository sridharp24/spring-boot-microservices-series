FROM openzipkin/zipkin:2.21
ADD ["target/zipkin-server-0.0.1-SNAPSHOT-exec.jar", "app.jar"]
EXPOSE 9411
ENV STORAGE_TYPE mem
ENV SCRIBE_ENABLED false
ENV SELF_TRACING_ENABLED true
ENV JAVA_OPTS="-Dlogging.level.zipkin=DEBUG"
RUN sh -c 'touch /app.jar'
ENTRYPOINT [ "sh", "-c", "java $JAVA_OPTS -Djava.security.egd=file:/dev/./urandom -Dspring.profiles.active=docker -jar /app.jar" ]
