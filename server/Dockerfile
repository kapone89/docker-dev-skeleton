FROM node:10.15-alpine AS development

RUN apk add --no-cache make gcc g++ python
RUN npm install -g yarn pm2

ENV APP_HOME /app
RUN mkdir $APP_HOME
WORKDIR $APP_HOME/server
