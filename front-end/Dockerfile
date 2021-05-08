FROM ubuntu:latest AS builder

USER root

WORKDIR /home/app

COPY listmod /home/app

RUN apt-get update

RUN apt-get -y install nodejs

RUN apt-get install npm -y

RUN npm install

RUN npm install -g @angular/cli

RUN npm install primeng --save

RUN npm install primeicons --save

RUN npm install @angular/animations --save --force

RUN ng build

FROM nginx:latest

COPY --from=builder /home/app/dist/listmod /usr/share/nginx/html

RUN apt-get update && \
    apt-get install -y wget

ENV DOCKERIZE_VERSION v0.6.1

RUN wget https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && tar -C /usr/local/bin -xzvf dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && rm dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz

