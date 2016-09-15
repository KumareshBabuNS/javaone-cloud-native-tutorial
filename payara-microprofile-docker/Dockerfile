FROM java:8-jdk-alpine

ENV PKG_FILE_NAME payara-mp-conference-schedule.jar
ENV PAYARA_PATH /opt/payara

RUN mkdir -p $PAYARA_PATH/deployments
RUN adduser -D -h $PAYARA_PATH payara && echo payara:payara | chpasswd
RUN chown -R payara:payara /opt

# Default payara ports to expose
EXPOSE 4848 8009 8080 8181

USER payara
WORKDIR $PAYARA_PATH

COPY $PKG_FILE_NAME $PAYARA_PATH

CMD java -jar $PKG_FILE_NAME
