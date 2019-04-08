# Helm Tiller for arm32v7

Tiller is built for arm but not in containerized 
so here it is.
Hopefully this get through: https://github.com/helm/helm/pull/5039


# Build
```
docker build -t tiller:arm32v7 -f Dockerfile.arm32v7 . 
```

# Deploy 

```
helm init \
    --upgrade \
    --node-selectors "beta.kubernetes.io/os"="linux" \
    --node-selectors "beta.kubernetes.io/arch"="arm" \
    --tiller-image tiller:arm32v7
```
