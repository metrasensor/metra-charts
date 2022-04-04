# Rancher Server

## Install

Первоначальная установка Rancher сервера.

```
sudo docker run -d --restart=unless-stopped \
  -e CATTLE_BOOTSTRAP_PASSWORD=V5fvB4R4XWQv7kc6jQ \
  -p 80:80 -p 443:443 \
  --privileged \
  --name rancher-server-262 \
  rancher/rancher:v2.6.2 \
  --acme-domain k8s.metrasensor.com
```

- [Подробная инструкция по установке](https://habr.com/ru/post/562588/)

## Upgrade

1. Остановите контейнер

```bash
sudo docker stop rancher-server-262
```

2. Создайте контайнер данных из остановленного контейнера

```bash
sudo docker create --volumes-from rancher-server-262 \
  --name rancher-data rancher/rancher:v2.6.2
```

3. Создайте архивную копию образа

```bash
sudo docker run --volumes-from rancher-data-262 -v "$PWD:/backup" \
  --rm busybox tar zcvf /backup/rancher-data-backup-262-<DATE>.tar.gz \
  /var/lib/rancher
```

4. Загрузите новую версию Rancher

```bash
sudo docker pull rancher/rancher:<RANCHER_VERSION_TAG>
```

5. Запустите новый контейнер Rancher сервера

```bash
sudo docker run -d --volumes-from rancher-data-262 \
  --restart=unless-stopped \
  -p 80:80 -p 443:443 \
  --privileged \
  --name rancher-server-<VERSION> \
  rancher/rancher:<RANCHER_VERSION_TAG>
  --acme-domain k8s.metrasensor.com
```

- [Подробная инструкция по обновлению версии Kubernetes](https://rancher.com/docs/rancher/v2.5/en/cluster-admin/upgrading-kubernetes/)

## Backup and Restore

- [Подробная инструкция по Backup and Restore Docker Volumes](https://docs.docker.com/storage/volumes/#backup-restore-or-migrate-data-volumes)
- [Подробная инструкция по Backup and Restore Rancher](https://rancher.com/docs/rancher/v2.5/en/backups/)


```bash
# Привязка селектора к наймспасй
scheduler.alpha.kubernetes.io/node-selector: space=metra
```