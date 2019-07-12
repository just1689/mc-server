# MC-server

The idea here is to spin up a Minecraft server using Spigot and MCMMO in Docker swarm. This will give you a server you can play on with friends and it will auto restart. It also ensures you can move it / back it up.

## Deploy existing container
- Install Docker
- Init the swarm `docker swarm init`
- Create the volumes
```bash
docker volume create mc-vol
```
- Create the service
```bash
docker service create --name mc --publish  25565:25565 --mount type=volume,source=mc-vol,destination=/mc just1689/mc-server:latest
```

## Building yourself

### Pre-requisites
- Install Git. 
- Install JDK8, make sure java is in path. 
- Install maven, check maven is in path.

### Build spigot
- Clone the repo
- `cd mc-server/bt`
- Build Spigot 1.14.3 `java -jar BuildTools.jar --rev 1.14.3`
- `mv spigot-1.14.3.jar ../container/mc`

### Add plugs 
- `cd mc-server/container/mc`
-  

