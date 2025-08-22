## NGINX Helm Chart

### Install

```bash
helm install my-nginx /workspace/charts/nginx
```

### Customize

```bash
helm install my-nginx /workspace/charts/nginx \
  --set image.repository=nginx \
  --set image.tag=1.27.3-alpine \
  --set replicaCount=2 \
  --set service.type=LoadBalancer \
  --set service.port=80
```

### Ingress

```bash
helm install my-nginx /workspace/charts/nginx \
  --set ingress.enabled=true \
  --set ingress.className=nginx \
  --set ingress.hosts[0].host=example.com \
  --set ingress.hosts[0].paths[0].path=/ \
  --set ingress.hosts[0].paths[0].pathType=Prefix
```

### Upgrade

```bash
helm upgrade my-nginx /workspace/charts/nginx -f values.yaml
```

### Uninstall

```bash
helm uninstall my-nginx
```