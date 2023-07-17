# gameServers

## Quick Start

### Insurgency

##### First time:
```
docker-compose build --force-rm steamcmd && \
docker-compose build --force-rm base-insurgency
```

##### Config (Optional)

Copy template and edit the server params

```cp docker-compose.override.yml.template  docker-compose.override.yml```

##### Run Server

Once the base image is created you can create multiple servers with different configurations in seconds

```docker-compose up -d insurgency```


## Steam Docs

https://developer.valvesoftware.com/wiki/SteamCMD#Downloading_SteamCMD

## Steamcmd Custom image:

``` docker-compose build --force-rm steamcmd ```

## Base Image

To avoid downloading the game app every time the container is recreated (change runtime parameters) we use an intermediate image. This image runs steamcmd with the necessary arguments for each app. You only need to build it the first time you use a steam app

### Build:

```
# docker-compose build --force-rm base-<APPNAME>
# For example:
docker-compose build --force-rm base-insurgency
```

### App Config

Use the docker-compose.override.yml.template to change runtime params and mount custom config files
