FROM ubuntu

RUN apt-get update
RUN apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_18.x | bash -
RUN apt-get upgrade -y
RUN apt-get install -y nodejs

COPY models models
COPY package.json package.json
COPY package-lock.json package-lock.json
COPY src src

RUN npm install

ENTRYPOINT [ "node", "/src/server.js" ]