FROM openjdk:8

COPY listmod /usr/src/myapp

WORKDIR /usr/src/myapp/

RUN apt-get update && \
    apt-get -y install maven && \
    apt-get install -y wget

RUN mvn -f pom.xml clean package

RUN mkdir /opt/deploy 

RUN cp /usr/src/myapp/target/listmod-1.0.0.jar /opt/deploy/listmod.jar

RUN cd /opt/deploy

ENV DOCKERIZE_VERSION v0.6.1

RUN wget https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && tar -C /usr/local/bin -xzvf dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && rm dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz

ENTRYPOINT ["java", "-jar", "/opt/deploy/listmod.jar"]



