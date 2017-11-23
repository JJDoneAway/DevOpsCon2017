# From 0 to 100 7 Workshop: Docker, Kubernetes and OpenShift
- Michael Johann, Crossbow GmbH
https://github.com/wjax2017/workshop


##Docker
### linking containers
```
docker run --name jo-mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql
docker run --name my-wordpress -p 81:80 --link jo-mysql:mysql -d wordpress
```
--link {my image name}:{to the internam environment}

### get persistence
will store the content on the local machine
```
docker run --name jo-mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql -v $(pwd)/data/mysql:/var/lib/mysql
```

### docker inspect
```
docker inspect jo-mysql
```
- if you stop the content inside the container will stay. but if you do docker rm jo-mysql it is deleted

### docker-machine
- it is able to spin up VM with docker demon in the cloud
```
docker-machine create --driver digitalocian --digital-ocean-access-token xyz
```
-if you do docker-machine ls you see all your machines
```
docker-machine env mynewenv
```
switches the remote docker to my local one

## docker compose
- docker compose is bundling more docker commands to spin up multiple containers at once
```
docker-compose up
```

## Kubernetes
