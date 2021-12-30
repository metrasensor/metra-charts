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

* [Подробная инструкция по обновлению Rancher server](https://rancher.com/docs/rancher/v2.5/en/installation/other-installation-methods/single-node-docker/single-node-upgrades/)
* [Подробная инструкция по обновлению версии Kubernetes](https://rancher.com/docs/rancher/v2.5/en/cluster-admin/upgrading-kubernetes/)

## Backup and Restore

* [Подробная инструкция по Backup and Restore Rancher](https://rancher.com/docs/rancher/v2.5/en/backups/)

