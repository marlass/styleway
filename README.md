# Styleway

Styleway is a tool for creating style guides.

## Architecture

- app consist of 4 main containers
- nginx for proxy to api and web app
- api in node.js with express
- web app build with next.js (react kit)
- mongodb for api to store all the data

## Development

For development docker-compose.yml was created. To run in you simply run `docker-compose up` in your terminal (make sure you have docker and docker-compose installed on your machine). It runs all the containers and map your repositories files. For web app it runs next.js in development mode and for api it rebuilds and restart express server with every change.

### Required plain structure

styleway - directory with docker-compose.yml
styleway-webapp - repository with web app files (currently private, ask for access)
styleway-api - repository with api files (currently private, ask for access)
styleway-data - directory for mongodb data

### Connecting to containers

If you want to execute command in the container (for example install dependencies without having yarn installed locally) you can connect to container using: `docker-compose exec webapp bash`. It will run shell in webapp container. To connect to api container just change webapp for api.

### Hosts

In nginx.conf file virtual hosts are specified to styleway.dev - for webapp and api.styleway.dev for api. To make it work on your computer add records in your hosts file pointing these hostnames to docker IP.

#### Linux example

In /etc/hosts add these records:

0.0.0.0 styleway.dev

0.0.0.0 api.styleway.dev
