# Rancher Server

## Install

```
docker run -d --restart=unless-stopped \
  -e CATTLE_BOOTSTRAP_PASSWORD=V5fvB4R4XWQv7kc6jQ \
  -p 80:80 -p 443:443 \
  -v /root/rancher:/var/lib/rancher \
  --privileged \
  --name rancher-server \
  rancher/rancher:latest \
  --acme-domain k8s.metrasensor.com
```

* [Подробная инструкция по установке](https://habr.com/ru/post/562588/)

## Upgrade

* TODO

## Backup and Restore

* TODO