FROM ubuntu:trusty

RUN apt-get update
RUN apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -
RUN apt-get -y install nodejs
RUN apt-get -y install build-essential
RUN apt-get -y install iptables

WORKDIR /usr/src/app

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 3000

COPY ./docker/entrypoint.sh /
RUN chmod +x /entrypoint.sh

# ENTRYPOINT ["/entrypoint.sh"]

CMD [ "node", "index.js" ]
