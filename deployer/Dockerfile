FROM ubuntu:20.04

RUN apt-get update

RUN apt-get install software-properties-common vim curl apt-utils openssh-client -y

RUN add-apt-repository ppa:ondrej/php

RUN apt-get install php8.1-common php8.1-curl php8.1-zip php8.1-cli -y

CMD [ "php", "-a" ]