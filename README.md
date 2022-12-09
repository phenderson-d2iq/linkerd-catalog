# linkerd-catalog
## This is a custom catalog for Linkerd for Kommander

![Linkerd Catalog](./image.png)

To add the Linkerd catalog to DKP,  run the following:

```
kubectl apply -f - <<EOF
apiVersion: source.toolkit.fluxcd.io/v1beta1
kind: GitRepository
metadata:
  name: linkerd-catalog-repo
  namespace: kommander
  labels:
    kommander.d2iq.io/gitapps-gitrepository-type: catalog
    kommander.d2iq.io/gitrepository-type: catalog
spec:
  interval: 1m0s
  ref:
    branch: main
  timeout: 20s
  url: https://github.com/phenderson-d2iq/linkerd-catalog
EOF
```

