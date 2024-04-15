```
helm create my-app
helm template . -f values.yaml > output.yaml
helm install my-awsome-app . --namespace our-app --create-namespace
```