# metra-helm
[![Chart Lint](https://github.com/metrasensor/metra-charts/actions/workflows/testing.yaml/badge.svg)](https://github.com/metrasensor/metra-charts/actions/workflows/testing.yaml)

## Добавление репозитория
```bash
helm repo add metra-registry \
'https://$GH_SECRET@raw.githubusercontent.com/metrasensor/metra-charts/master/charts'
```
## Создание чарта
```bash
helm create $CHART_NAME
```

## Публикация пакетов
```bash
$ helm package metra-app
$ mv metra-app-0.1.0.tgz charts
$ helm repo index charts/ --url raw.githubusercontent.com/metrasensor/metra-charts/master/charts
```