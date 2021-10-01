# Running Your First Docker Container
The ```docker run``` command ***creates*** a writeable container over a
specified image and then ***starts*** it using the specified command. A stopped
container can be restarted with all of its previous changes intact using
```docker start```.

See ```docker ps -a``` to list all containers.


## Usage
```bash
docker run [OPTIONS] IMAGE [COMMAND] [ARGS...]
docker start [OPTIONS] CONTAINER [CONTAINER...]
```


## Beginner Options
|    Command    |    Summary                                            |
|    :-:        |    -                                                  |
|    -i         |    Keep STDIN open even if not attached               |
|    -t         |    Allocate a pseudo-TTY                              |
|    --rm       |    Automaticallly remove a container when it exits    |

Please note that ```--rm``` removes the container when it exits, but not the 
container image. For example:
```bash
docker run -it --rm ubuntu
```
All the changes made to that container image instance will be lost when you
exit; however, the base ***ubuntu image*** will remain. Running the same command
without ```-rm``` will save the container upon exiting, but not overwrite the
ubuntu image.

To get a list of all the containers on your system:
```bash
docker container ls -a
```


## Related
[202110010257](../202110010257) - Install Docker on Linux \
[202110010028](../202110010028) - What's a Container and Why Should You Care?


## Tags
#containers #docker
