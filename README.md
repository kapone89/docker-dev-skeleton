# How to run API server using Docker

## Requirements

* Docker: https://docs.docker.com/docker-for-mac/install/
* Docker Compose: https://docs.docker.com/compose/install/

## Setup

* make sure docker daemon is running `docker ps`
* run `bin/docker setup-server` (skip if you don't want to run server in Docker)
* run `bin/docker setup-web` (skip if you don't want to run web in Docker)

Setup commends will install node packages, prepare database and seed initial data

## How to run (once it's setup)

* just run `bin/docker start`
* open http://localhost:8080
* sign-in using `user1@example.com / test123`

## To remove all containers, images and volumes (data)

* run `bin/docker prune`

## To run web (frontend), ensuring that server is running and available on localhost:3000

* `bin/docker web`

## To run server (API)

* `bin/docker server`

## To run other services and databases (like postgresql, mailcatcher, etc.)

* `bin/docker services`

You can connect to postgresql using external client on port 5432. Mailcatcher web interface is exposed on port 1080.

## Typical scenarios

### QA: run everything form docker

* `bin/docker start`

### FE: development: run server only, web from local node

* `bin/docker server`
* `cd web && yarn start`

### BE: development: run services & web only, server from local node

* `bin/docker services`
* `bin/docker web`
* `cd server && yarn start:watch`

## Important

When you are switching from running server in a docker using `bin/docker server` to running it
localy using `cd server && yarn start:watch`, you have to clean `node_modules` dir first
and reinstall all packages.

You don't have to install node locally to develop the app. You can use `bin/docker server`
and `bin/docker web`. However some of your develpment tools (like tslint plugin for vs code) will not work without node installed in your system.
