### DOCKER COMMONLY USED COMMANDS

##### Show all containers
    docker ps

##### Show all running containers
    docker ps -a

##### Show all running containerIds
    docker ps -aq

##### Delete all containers
    docker rm -f $(docker ps -aq)

or

    docker ps -aq | xargs docker rm -f
    
##### Delete all stopped containers
    docker container prune

without prompt

    docker container prune -f

alternate way

    docker rm $(docker ps -a -q -f status=exited)

##### Show container logs
    docker logs <CONTAINER_ID or NAME>
    



