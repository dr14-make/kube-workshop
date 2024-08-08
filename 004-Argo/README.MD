Using CRD (Custom Resource Definition )
Two main resources :
 - Application
 - Application set (different type of generators)


```
helm repo add argo https://argoproj.github.io/argo-helm
helm search repo argo
helm show values argo/argo-cd > values.yaml
kubectl create namespace argocd
helm install argocd argo/argo-cd --namespace argocd
```