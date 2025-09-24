FROM eclipse-temurin:17.0.4.1_1-jdk-centos7
WORKDIR /app
COPY target/openisle-0.0.1-SNAPSHOT.jar app.jar
RUN groupadd openisle && \
    useradd -u 65530 -g openisle openisle && \
    mkdir logs && \
    chmod a+rw logs && \
    chown -R openisle:openisle .
USER 65530
ENTRYPOINT ["sh", "-c", "java ${JAVA_OPTS} -jar app.jar >/dev/null  2>&1"]