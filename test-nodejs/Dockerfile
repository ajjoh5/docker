FROM ubuntu:14.04

## Get the WGET downloader (downloads files from URLs)
RUN apt-get install -y wget

## Get the latest NodeJS dist
RUN wget https://nodejs.org/dist/v5.2.0/node-v5.2.0-linux-x64.tar.gz

## Unzip the latest NodeJS dist to /usr/local
RUN tar -C /usr/local --strip-components 1 -xzf node-v5.2.0-linux-x64.tar.gz
RUN rm node-v5.2.0-linux-x64.tar.gz

ADD /nodejs/package.json /web/package.json
RUN cd web; npm install

ADD /nodejs /web

EXPOSE 3000

CMD ["node", "/web/server.js"]