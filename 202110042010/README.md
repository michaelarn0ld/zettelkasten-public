# Making a Workspace Container With Docker
By default, docker will give your container a random name and a random hostname.
For the purposes of a workspace container, we will want to make sure that our
docker container is easily identifiable.


## Setting the Docker Options
```bash
docker run -it --name $NAME -h $HOSTNAME $IMAGE
```
It is not a bad idea to set ```$NAME``` and ```$HOSTNAME``` as the same value 
for easy identifying. Please note that we are not using ```--rm``` which means
that the container will be saved for reuse upon exiting.


## Related
[202110012243](../202110012243) - Using Basic Docker Commands
[202110011837](../202110011837) - Running Your First Docker Container


## Tags
#containers #docker
