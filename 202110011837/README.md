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


## Related
[202110010257](../202110010257) - Install Docker on Linux
[202110010028](../202110010028) - What's a Container and Why Should You Care?


## Tags
#containers #docker
