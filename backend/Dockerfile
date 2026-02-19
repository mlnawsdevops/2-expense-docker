# DB_HOST is mysql container name because mysql netowrk ip is not stable so we are using container name for stability purpose

FROM node:20.18.0-alpine3.20
EXPOSE 8080
ENV DB_HOST=mysql
RUN addgroup -S expense && adduser -S expense -G expense
RUN mkdir /opt/server
RUN chmod -R expense:expense /opt/server
WORKDIR /opt/server
COPY package.json .
COPY *.js .
# dependency install
RUN npm install
# start the nodejs
USER expense
CMD ["node", "index.js"]

# FROM node:20
# EXPOSE 8080
# ENV DB_HOST=mysql
# RUN mkdir /opt/server
# WORKDIR /opt/server
# COPY package.json .
# COPY *.js .
# # dependency install
# RUN npm install
# # start the nodejs
# CMD ["node", "index.js"]
