# Using Basic Docker Commands

|    Commands   |    Summary                                                   |
|    :-:        |    -                                                         |
|    pull       |    pull an image or repository from a registry               |
|    run        |    create a new instance of a container from an image        |
|    start      |    start one or more stopped containers                      |
|    stop       |    stop one or more started containers                       |
|    attach     |    attach local stdin, stdout, stderr to a running container |
|    images     |    list all the container images                             |
|    ps         |    list running containers (-a to include idle containers)   |
|    container  |    manage containers (container rm to remove containers)     |
|    rmi        |    remove one or more images                                 |

*You can detach from an attached container using ```Ctrl+pq```
*You can exit from an attached container using ```exit```

Exiting a container is different from detaching from a container. The former
stops the container and detaches; the latter only detaches from the container
but the container is still left running and consuming resources.


## Tags
#docker
