# docker-tutorial

### [docker-hub](https://hub.docker.com/)

### Running a docker image

- `docker pull redis`
- `docker images`
- `docker run redis`
- `docker ps`
- detach mode `docker run -d redis`
- `docker stop <container-id>`
- `docker start <container-id>`
- `docker ps -a`
- `docker run redis:4.0`
  ![image](https://user-images.githubusercontent.com/26702243/173348941-72a40133-78d9-42e6-9c2d-60bcedae10a6.png)
- `docker run -p <port>:6379 redis:4.0`
  ![image](https://user-images.githubusercontent.com/26702243/173350609-0b20af5d-49a4-4d66-8aff-9f81ffbc463e.png)
- `docker logs`

### Manage a docker container
![image](https://user-images.githubusercontent.com/26702243/178422388-4d98871d-7901-41fc-b853-65d5e84d210d.png)
