FROM java:8-jdk-alpine
RUN  apk add -U tzdata && \
     ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
COPY ./target/portal-service.jar ./
COPY pinpoint /pinpoint
EXPOSE 8080
CMD java -jar -javaagent:/pinpoint/pinpoint-bootstrap-1.8.5.jar -Dpinpoint.agentId=${HOSTNAME} -Dpinpoint.applicationName=ms-protal /portal-service.jar
