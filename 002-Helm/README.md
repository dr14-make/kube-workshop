```
helm create my-test-app
cd my-test-app
helm template . -f values.yaml > output.yaml
helm install my-awsome-app . --namespace our-app --create-namespace
```