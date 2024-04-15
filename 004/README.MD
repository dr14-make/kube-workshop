```
helm repo add argo https://argoproj.github.io/argo-helm
helm search repo argo
helm show values argo/argo-cd > values.yaml
kubectl create namespace argocd
```