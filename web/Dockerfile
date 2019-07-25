FROM node:10.15-alpine AS development

RUN npm install -g yarn

ENV APP_HOME /app
RUN mkdir $APP_HOME
WORKDIR $APP_HOME/web
