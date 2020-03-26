# Below are some useful Docker Commands #

### 1. Install Docker in Amazon Linux 2

```
sudo amazon-linux-extras install docker
```

### 2. Start Docker Service

```
sudo service docker start
```

### 3. Add ec2-user to the docker group so you can execute Docker commands without using sudo. 

```
sudo usermod -a -G docker ec2-user
```

### 6. Docker Information

```
docker info [OPTIONS]

Example:  docker info
          docker -D info [ -D option causes all docker commands to output debug information.]
          docker info --format '{{json .}}'  [ --format : specify the output format ]          
```
For option list visit [https://docs.docker.com/engine/reference/commandline/info/](https://docs.docker.com/engine/reference/commandline/info/)

### 5. Build Docker

```
docker build [option] PATH | URL | -

Example: docker build .
         docker build -f ctx/Dockerfile http://server/ctx.tar.gz
         docker build https://server/context.tar.gz
         docker build - < Dockerfile
```         
For option list visit [https://docs.docker.com/engine/reference/commandline/build/](https://docs.docker.com/engine/reference/commandline/build/)

### 6. Create Docker

```
docker create [options] IMAGE

Example: docker create --name container_name --expose port_number image_name
         docker create -it --storage-opt size=120G fedora /bin/bash
         docker create -v /data --name data ubuntu
```
For option list visit [https://docs.docker.com/engine/reference/commandline/create/](https://docs.docker.com/engine/reference/commandline/create/)

### 7. Run Docker

```
docker run [options] IMAGE

Example: docker run -it debian:buster /bin/bash
         docker run -t -i --rm ubuntu bash
         docker run -p 127.0.0.1:80:8080/tcp ubuntu bash
```
For option list visit [https://docs.docker.com/engine/reference/commandline/run/](https://docs.docker.com/engine/reference/commandline/run/)

### 8. Execute Docker

```
docker exec [options] CONTAINER COMMAND

Example: docker exec app_web_1 tail logs/development.log
         docker exec -it ubuntu_bash bash
         docker exec -d ubuntu_bash touch /tmp/logFile

Note: If the container is paused, then the docker exec command will fail with an error.
```
For option list visit [https://docs.docker.com/engine/reference/commandline/exec/](https://docs.docker.com/engine/reference/commandline/exec/)

### 9. Start Docker

```
docker start [options] CONTAINER

Example: docker start container_name
         
```
For option list visit [https://docs.docker.com/engine/reference/commandline/start/](https://docs.docker.com/engine/reference/commandline/start/)

### 10. Stop Docker

```
docker stop [options] CONTAINER

Example: docker stop container_name
         docker stop --time 30 container_name [ --time/ -t : Seconds to wait for stop before killing it ]
```

### 11. Docker log

```
docker logs [OPTIONS] CONTAINER

Example: docker logs -f --until=2s
         docker logs $ID
         docker logs $ID 2>&1 | less
```
For option list visit [https://docs.docker.com/engine/reference/commandline/logs/](https://docs.docker.com/engine/reference/commandline/logs/)

### 12. List Docker Container

```
docker ps [OPTIONS]

Example: docker ps
         docker ps -a [ --all/-a : List all container ]
         docker ps -s [ --size/-s : List size of all container]
         docker ps -a --filter 'exited=0'
         docker ps --filter status=running
         docker ps --filter expose=8000-8080/tcp
```
For option list visit [https://docs.docker.com/engine/reference/commandline/ps/](https://docs.docker.com/engine/reference/commandline/ps/)

### 13. List Docker Image

```
docker images [OPTIONS]

Example: docker images
         docker images -a
         docker images --no-trunc [ List the full length image IDs ]
         docker images --digests [ Images that use the v2 or later format ]
         docker images --filter "dangling=true" [ Show untag images list]
```
For option list visit [https://docs.docker.com/engine/reference/commandline/images/](https://docs.docker.com/engine/reference/commandline/images/)

### 14. Remove Docker Container

```
docker rm [OPTIONS] CONTAINER

Example: docker rm b750ce38469a
         docker rm --link /webapp/redis
         docker rm --force redis
         docker rm -v redis

```
For option list visit [https://docs.docker.com/engine/reference/commandline/rm/](https://docs.docker.com/engine/reference/commandline/rm/)

### 15. Remove Docker Images

```
docker rmi [OPTIONS] IMAGE

Example: docker rmi bc435f29654a
         docker rmi -f cd184b17914f

```
For option list visit [https://docs.docker.com/engine/reference/commandline/rmi/](https://docs.docker.com/engine/reference/commandline/rmi/)

### 16. Docker Cleanup

```
docker system prune [ Cleans up dangling images, containers, volumes, and networks that is not associated with a container ]
docker system prune -a [ Additionally remove any stopped containers and all unused images ]
docker system prune -a --volumes [ prune volumes also ]
docker rm $(docker ps -a -q) [ Remove all stopped containers ]
docker rmi $(docker images | grep "^<none>" | awk "{print $3}") [ Remove all untagged Images ]
```
      
