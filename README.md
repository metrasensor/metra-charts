# metra-helm

[![Chart Lint](https://github.com/metrasensor/metra-charts/actions/workflows/testing.yaml/badge.svg)](https://github.com/metrasensor/metra-charts/actions/workflows/testing.yaml)

## Добавление репозитория

```bash
helm repo add metra-registry \
'https://metrasensor.github.io/metra-charts/'
```

## Создание чарта

```bash
helm create $CHART_NAME

# Проверка чарта
helm template $CHART_NAME
```

## Публикация пакетов

```bash
$ helm package metra-app
$ mv metra-app-0.1.0.tgz docs
$ helm repo index docs/ --url https://metrasensor.github.io/metra-charts/ --merge index.yaml
