FROM ubuntu:16.04 as builder

RUN apt-get update && \
    apt-get install -y curl && \
    curl -sL https://deb.nodesource.com/setup_10.x | bash && \
    apt-get install -y git nodejs build-essential

RUN npm install -g node-gyp && \
    npm install -g typescript

WORKDIR /build
COPY ./src/package*.json ./
RUN npm install --only=production
COPY ./src/ .
RUN npm build


FROM node:10-alpine
WORKDIR /app/
COPY --from=builder /build .
ENTRYPOINT [ "npm", "start" ]

# FROM node:8-alpine

# WORKDIR /usr/src/app

# COPY ./src/package*.json ./

# RUN npm install --only=production

# COPY ./src .

# EXPOSE 3978
# CMD [ "npm", "start" ]