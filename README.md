# Docker manage

Usefull information for managing docker containers

## Add user to docker group
Working with docker is a pain if yuo can not run it as your user. Therefore
add your user to the docker group

```
sudo usermod -aG docker $(whoami)
```

Log out and log in from your server to activate your new groups.


## Enable restart of docker and services at boot

In each aplications that should start at boot add in  `docker-compose.yml`
```
restart: always
```

## Container retart
Cron job to reateart containers every day at 01:00 at in order to maintain the overall health of apps
```
00 01 * * * docker restart $(docker ps -q)
```

## System restart 
Cron job to restart system every Saturday 00:30 week in order to maintain the overall health the system. This job needs to be run by root.
```
30 00 * * 6 reboot
```

## Removed all `<none>` taggded images


Run `docker rmi $(docker images -f "dangling=true" -q --no-trunc)` to remove all images with repository and tag filed set to`<none>` ([reference](https://docs.docker.com/engine/reference/commandline/images/)

## Buld latest 
If not the latest LTS realease of jenkins is on there official docker hub one can go ahead and
clone there [docker repository](https://github.com/jenkinsci/docker) 
and build it your self. Just change version in the `Dockerfile` and then run
```
docker build . --tag jenkins:{version}
```

Volia!

## Pipelines
Need to go to global tool configurations and add grovvy installation
