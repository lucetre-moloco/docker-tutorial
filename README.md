# docker-tutorial

### [docker-hub](https://hub.docker.com/)

## Running a docker image

- `docker pull redis`
- `docker images`
- `docker run redis`
- `docker ps`
- detach mode `docker run -d redis`
- `docker stop <container-id>`
- `docker start <container-id>`
- `docker rm <container-id>`
- `docker ps -a`
- `docker run redis:4.0`
  ![image](https://user-images.githubusercontent.com/26702243/173348941-72a40133-78d9-42e6-9c2d-60bcedae10a6.png)
- `docker run -p <port>:6379 redis:4.0`
  ![image](https://user-images.githubusercontent.com/26702243/173350609-0b20af5d-49a4-4d66-8aff-9f81ffbc463e.png)
- `docker logs`

## Manage a docker container

![image](https://user-images.githubusercontent.com/26702243/178422388-4d98871d-7901-41fc-b853-65d5e84d210d.png)

## Demo project

- Create mongo network
  - Check via `docker network ls`
  - `docker network create mongo-network`
- Download image
  - `docker pull mongo`
  - `docker pull mongo-express`
- [Run mongo server](https://hub.docker.com/_/mongo)
  - ```
    docker run -d \
      -p 27017:27017 \
      -e MONGO_INITDB_ROOT_USERNAME=admin \
      -e MONGO_INITDB_ROOT_PASSWORD=password \
      --name mongodb \
      --net mongo-network \
      mongo
    ```
  - `docker start mongodb`
  - `docker logs mongodb`
- [Run mongo express](https://hub.docker.com/_/mongo-express)
  - ```
    docker run -d \
      -p 8081:8081 \
      -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin \
      -e ME_CONFIG_MONGODB_ADMINPASSWORD=password \
      -e ME_CONFIG_MONGODB_SERVER=mongodb \
      --name mongo-express \
      --net mongo-network \
      mongo-express
    ```
  - `docker start mongo-express`
  - `docker logs mongo-express`
  - Connect [localhost:8081](http://localhost:8081)
  - Open node.js server
    - `npm install`
    - `node server.js`

## Docker compose

- `docker-compose -f mongo.yml up`
- `docker-compose -f mongo.yml down`
  - `docker network ls`
  - `docker ps`

## Dockerfile

- Blueprint for creating docker images
- ``
