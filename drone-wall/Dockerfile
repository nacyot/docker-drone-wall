FROM node

RUN \
  apt-get update &&\
  apt-get install -y git curl wget

RUN git clone https://github.com/drone/drone-wall.git /app
WORKDIR /app
RUN \
  npm install &&\
  npm install -g bower &&\
  npm install -g grunt-cli &&\
  bower --allow-root install &&\
  grunt deploy

EXPOSE 3000
CMD API_SCHEME=$API_SCHEME API_DOMAIN=$API_DOMAIN API_TOKEN=$API_TOKEN node server.js
