FROM node:14.5.0-alpine
# I am creating system group and user named cart
RUN addgroup -S cart && adduser -S cart cart
EXPOSE 8080
WORKDIR /opt/server
RUN chown -R cart:cart /opt/server
USER cart
COPY package.json /opt/server/
RUN npm install
COPY server.js /opt/server/
CMD ["node", "server.js"]

