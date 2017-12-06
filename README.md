Docker image with the [Monitorr](https://github.com/Monitorr/Monitorr "Monitorr") and [Logarr](https://github.com/Monitorr/logarr "Logarr") projects built-in.

#### Usage
```
docker create \
  --name=monitorr-logarr \
  --restart=on-failure \
  -v <host path for config:/config \
  -v <host path for logs>:/var/log \
  -e TZ=<timezone> \
  -p 80:80 \
  tronyx/docker-monitorr-logarr
```

#### Parameters
* `--name` - The name of the container - Call it whatever you want.
* `--restart=on-failure` Container restart mode - Docker attempts to restarts the container if the container returns a non-zero exit code. More info [HERE](https://docs.docker.com/engine/admin/start-containers-automatically/ "HERE") on container restart policies.
* `-v /home/logarr/config:/config` - Your preferred app data config path, IE: where you're storing the Logarr config files.
* `-v /home/logarr/config/log:/var/log` Your preferred app log path, IE: where you're storing the Logarr, Nginx, and PHP logs.
* `-e TZ` - Your timezone, IE: `America/New_York`.

### Info
* To monitor the logs of the container in realtime `docker logs -f logarr`
