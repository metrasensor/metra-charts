# metra-helm

```
https://medium.com/hackernoon/using-a-private-github-repo-as-helm-chart-repo-https-access-95629b2af27c

https://habr.com/ru/company/vk/blog/516934/

helm repo add metra-registry 
'https://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@raw.githubusercontent.com/metrasensor/metra-helm/master/charts'

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

https://github.com/metrasensor/metra-helm.git
```
Публикация пакетов
```
$ helm package my-app
$ mv my-app-0.1.0.tgz charts
$ helm repo index charts/ --url raw.githubusercontent.com/metrasensor/metra-charts/master/charts
```