FROM openjdk:11-jre-slim

WORKDIR /opt/traccar

RUN apt update && apt install -y wget unzip

# Download Traccar
RUN wget -O traccar.zip https://github.com/traccar/traccar/releases/download/v5.10/traccar-other-5.10.zip \
    && unzip traccar.zip -d . \
    && rm traccar.zip

# Copy configuration file (if modified)
COPY traccar.xml /opt/traccar/conf/traccar.xml

EXPOSE 8082

CMD ["java", "-jar", "tracker-server.jar", "conf/traccar.xml"]
