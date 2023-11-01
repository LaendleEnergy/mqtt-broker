FROM eclipse-mosquitto:2.0-openssl

COPY ./conf/mosquitto.conf /mosquitto/config/mosquitto.conf

RUN mkdir /mosquitto/certs
RUN mkdir /mosquitto/certs/client

COPY ./certs/ca.crt /mosquitto/certs
COPY ./certs/client/client.key /mosquitto/certs/client
COPY ./certs/client/client.crt /mosquitto/certs/client

EXPOSE 1883