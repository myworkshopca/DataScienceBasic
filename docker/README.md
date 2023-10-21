# Use Docker Compose for Local Jupyter Notebook Development

Docker compose will provide an easy and clean development environment for
Jupyter Notebook.

## install Docker Desktop

Follow Docker website to install [Docker Desktop](https://www.docker.com/products/docker-desktop/).

Check docker desktop after installation
```bash
docker compose --help
```

## Docker Compose build create and starte Jupyter server

```vim
%s/rd\/myworkshopca\/DataScienceBasic/abc/gc
```

```bash
# go to docker folder of your local,
# my local is ~/abc/docker
cd ~/rd/myworkshopca/DataScienceBasic/docker; ls -la

# check the current status.
cd ~/rd/myworkshopca/DataScienceBasic/docker; docker compose ps
docker compose ls

# create image.
cd ~/rd/myworkshopca/DataScienceBasic/docker; docker compose create
cd ~/rd/myworkshopca/DataScienceBasic/docker; docker compose build

# start notebook server
cd ~/rd/myworkshopca/DataScienceBasic/docker; docker compose start
cd ~/rd/myworkshopca/DataScienceBasic/docker; docker compose restart
cd ~/rd/myworkshopca/DataScienceBasic/docker; docker compose stop
```

After the notebook container started, we could access the notebook from
[localhost:8888](http://localhost:8888).
It will ask a token to access notebooks.
Using the following commands to check docker logs to get token

```bash
cd ~/rd/myworkshopca/DataScienceBasic/docker; docker compose logs --help
cd ~/rd/myworkshopca/DataScienceBasic/docker; docker compose logs mynotebook
# option -f will tail the logging message.
# docker tail log
# CTRL-c to quit tailing.
cd ~/rd/myworkshopca/DataScienceBasic/docker; docker compose logs -f mynotebook
```

### explore the jupypter container folder tructure

We need find the work folder to map to local.
The Jupyter Notebook image is using user Jovyan and the work folder is /home/jovyan/work.
User: jovyan
Home folder: /home/jovyan
Work folder: /home/jovyan/work

```bash
docker exec mynotebook pwd
docker exec mynotebook ls -la
docker exec mynotebook ls -la work
```

### tear down everything

```bash
cd ~/rd/myworkshopca/DataScienceBasic/docker; docker compose down --help
# NOTE: this command will remove everything.
cd ~/rd/myworkshopca/DataScienceBasic/docker; docker compose down
## --rmi will remove images too,
cd ~/rd/myworkshopca/DataScienceBasic/docker; docker compose down --rmi all
```
