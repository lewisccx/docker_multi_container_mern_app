# using docker network to connect multiple containers
# to create a network
# docker network create goals-net
# docker network ls
# running mongodb service without network
# docker run -d --name mongodb -p 7070:27017 --rm -d mongo

# running mongodb service with network
# -p 7070:27017, publish port in optional here unless u want to access mongo from your localhost:7070
# docker run -d --name mongodb --network goals-net -p 7070:27017 mongo 

# to persist mongodb data
# docker run -d --name mongodb --network goals-net -v mongodb_data:/data/db -p 7070:27017 mongo

# to add authetication
# docker run -d --name mongodb --network goals-net -v mongodb_data:/data/db -p 7070:27017 -e MONGO_INITDB_ROOT_USERNAME=mongoadmin -e MONGO_INITDB_ROOT_PASSWORD=password mongo

# us '\' to split your long command 

# Docker compose command
### attached mode
> docker-compose up
### detached mode
> docker-compose up -d 
### remove all containers and network
> docker-compose down
### remove all containers, network and volumes
> docker-compose down -v
### to rebuild any image in docker-compose
#### just build
> docker-compose build 
#### build images before up
> docker-compose up --build`.

