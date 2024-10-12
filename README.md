## 👋 Welcome to proxymanager 🚀  

proxymanager README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update proxymanager
```
  
## Install and run container
  
```shell
mkdir -p "$HOME/.local/share/srv/docker/proxymanager/rootfs"
git clone "https://github.com/dockermgr/proxymanager" "$HOME/.local/share/CasjaysDev/dockermgr/proxymanager"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/proxymanager/rootfs/." "$HOME/.local/share/srv/docker/proxymanager/rootfs/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-proxymanager \
--hostname proxymanager \
-e TZ=${TIMEZONE:-America/New_York} \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-proxymanager/rootfs/data:/data:z" \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-proxymanager/rootfs/config:/config:z" \
-p 80:80 \
casjaysdevdocker/proxymanager:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdevdocker/proxymanager
    container_name: casjaysdevdocker-proxymanager
    environment:
      - TZ=America/New_York
      - HOSTNAME=proxymanager
    volumes:
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-proxymanager/rootfs/data:/data:z"
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-proxymanager/rootfs/config:/config:z"
    ports:
      - 80:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/proxymanager
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/proxymanager" "$HOME/Projects/github/casjaysdevdocker/proxymanager"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/proxymanager"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  
