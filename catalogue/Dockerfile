FROM node:20-alpine
RUN addgroup -S roboshop && roboshop -S appuser -G roboshop
#WORKDIR /opt/server
RUN chown -R roboshop:roboshop /opt/server
USER roboshop
COPY package.json .
COPY *.js .
RUN npm install
ENV MONGO="true" \
    MONGO_URL="mongodb://mongodb:27017/catalogue"
CMD ["node", "server.js"]