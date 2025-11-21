FROM node:20-alpine
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
WORKDIR /opt/server


COPY package.json .
COPY *.js .
RUN chown -R roboshop:roboshop /opt/server
RUN npm install
ENV MONGO="true" \
    MONGO_URL="mongodb://mongodb:27017/catalogue"
USER roboshop
CMD ["node", "server.js"]