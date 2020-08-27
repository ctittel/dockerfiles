# dockerfiles
My Dockerfiles

## Important Docker flags
### Use my user id and group id in the container
`-u $(id -u $USER):$(id -g $USER)`

### Get display 
`-e "DISPLAY" -v "/tmp/.X11-unix:/tmp/.X11-unix:rw"`

### Use first GPU
`--gpus '"device=0"'`
