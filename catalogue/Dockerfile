FROM node:14.5.0-alpine

EXPOSE 8080
RUN addgroup -S catalogue && adduser -S catalogue catalogue
WORKDIR /opt/server
RUN chown -R catalogue:catalogue /opt/server
USER catalogue
COPY package.json /opt/server/

RUN npm install

COPY server.js /opt/server/

ENTRYPOINT ["node", "server.js"]

