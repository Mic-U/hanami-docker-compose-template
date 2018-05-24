# Hanami-Docker-Compose-Template

## Requirement

* [Docker](https://www.docker.com)
* [Docker-Compose](https://docs.docker.com/compose/)
  
Unrecommended: Using on Windows Machine

## Container Architecture

See docker-compose.yml file

* app
  * Hanami application container
  * Using Dockerfile in project root. 
* mysql
  * Database container
  * Using official docker image mysql:latest.
* adminer
  * Container for managing DB.
  * Using official docker image adminer:latest.

## How to Use

### 1. Clone From Github

`git clone git@github.com:Mic-U/hanami-docker-compose-template.git`

### 2. Build Hanami image

`docker-compose build`

### 3. Start Application

`docker-compose up -d`

  
Without `-d` option, you can see stdout.  
`docker-compose up`

### 4. Run hanami commands

You can use rake or hanami commands on container.  
`docker-compose run --rm app bundle exec hanami db create` 

And You can use environment variables.  
If you want to set HANAMI_ENV test, run below command.  
`docker-compose run --rm -e HANAMI_ENV=test app bundle exec hanami db create`

Recommend using alias. 

### 5. Stop Application

`docker-compose down`
