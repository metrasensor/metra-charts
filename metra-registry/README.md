```bash
kubectl create secret docker-registry metra-registry-secret /
        --docker-server=ghcr.io /
        --docker-username=neegor /
        --docker-password=$GH_SECRET /
        --docker-email=gorschal@gmail.com
```
