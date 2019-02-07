FROM openjdk:8u171-jre-alpine

RUN echo "http://dl-2.alpinelinux.org/alpine/v3.7/main" >> /etc/apk/repositories      && \
    echo "http://dl-2.alpinelinux.org/alpine/v3.7/community" >> /etc/apk/repositories && \
    echo "http://dl-3.alpinelinux.org/alpine/v3.7/main" >> /etc/apk/repositories      && \
    echo "http://dl-3.alpinelinux.org/alpine/v3.7/community" >> /etc/apk/repositories && \
    echo "http://dl-4.alpinelinux.org/alpine/v3.7/main" >> /etc/apk/repositories      && \
    echo "http://dl-4.alpinelinux.org/alpine/v3.7/community" >> /etc/apk/repositories && \
    echo "http://dl-5.alpinelinux.org/alpine/v3.7/main" >> /etc/apk/repositories      && \
    echo "http://dl-5.alpinelinux.org/alpine/v3.7/community" >> /etc/apk/repositories

RUN apk --no-cache add curl
CMD java ${JAVA_OPTS} -jar ftgo-consumer-service.jar
HEALTHCHECK --start-period=30s --interval=5s CMD curl -f http://localhost:8080/actuator/health || exit 1
COPY build/libs/ftgo-consumer-service.jar .
