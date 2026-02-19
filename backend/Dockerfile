# DB_HOST is mysql container name because mysql network ip is not stable so we are using container name for stability purpose

# dockerfile-1 building the code
FROM node:20 AS builder
WORKDIR /opt/server
COPY package.json .
COPY *.js .
# dependency install
RUN npm install


# output from dockerfile-1 to compress the image in dockerfile-2
FROM node:20.18.0-alpine3.20
EXPOSE 8080
ENV DB_HOST=mysql
RUN addgroup -S expense && adduser -S expense -G expense && \
    mkdir /opt/server && \
    chown -R expense:expense /opt/server
WORKDIR /opt/server
COPY --from=builder /opt/server /opt/server
USER expense
# start the nodejs
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
