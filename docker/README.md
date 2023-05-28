# Use Docker Compose for Local Jupyter Notebook Development

Docker compose will provide an easy and clean development environment for
Jupyter Notebook.

## install Docker Desktop

Follow Docker website to install Docker Desktop.

Check docker desktop after installation
```bash
docker compose --help
```

## Docker Compose build create and starte Jupyter server

```bash
# go to docker folder of your local,
# my local is ~/rd/myworkshopca/DataScienceBasic/docker
cd ~/rd/myworkshopca/DataScienceBasic/docker; ls -la

# check the current status.
cd ~/rd/myworkshopca/DataScienceBasic/docker; docker compose ps
cd ~/rd/myworkshopca/DataScienceBasic/docker; docker compose ls

# create image.
cd ~/rd/myworkshopca/DataScienceBasic/docker; docker compose create
cd ~/rd/myworkshopca/DataScienceBasic/docker; docker compose build

# start notebook server
cd ~/rd/myworkshopca/DataScienceBasic/docker; docker compose start
cd ~/rd/myworkshopca/DataScienceBasic/docker; docker compose restart
```

check docker logs to get token

```bash
cd ~/rd/myworkshopca/DataScienceBasic/docker; docker compose logs --help
cd ~/rd/myworkshopca/DataScienceBasic/docker; docker compose logs mynotebook
# option -f will tail the logging message.
# docker tail log
cd ~/rd/myworkshopca/DataScienceBasic/docker; docker compose logs -f mynotebook
```

### explore the jupypter container folder tructure

We need find the work folder to map to local.
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
# NOTE: this command will remove everything.
cd ~/rd/myworkshopca/DataScienceBasic/docker; docker compose down
```
