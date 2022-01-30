# medium-docker-keep-running

### Build
```sh
docker build -t keeprun .
```

### Run
```sh
## Run normal
docker run -d --name myc keeprun

## Run with keep running
docker run -d --name myc keeprun tail -f /dev/null

### Alternatively inside Dockerfile
# ENTRYPOINT ["tail", "-f", "/dev/null"]
```

### SSH into container
```sh
docker exec -it myc /bin/sh
```

### Check logs
```sh
docker logs myc
```

### Remove container
```sh
## Use "--force" so it don't has to be stopped before
docker rm myc --force
```