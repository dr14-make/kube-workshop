 # Introduction

 Kubernetes is an open source container orchestration engine for automating deployment, scaling, and management of containerized applicatio

 ## Tools and extensions

1. kubectl

``` bash
brew install kubernetes-cli
```
2. Lens

``` bash
brew install --cask lens
```
Need to register and login

3. helm

``` bash
brew install kubernetes-helm
helm init
```

4. Enable kubernetes in docker desktop

![Alt text](images/docker-enable.png?raw=true "Title")


# What are we going to do?

1. Learn about basic kubernetes resources
    * Namespace
    * Pod
    * Service
    * Deployment
        * Replica Set
    * Secrets
    * Igres
2. Learn about helm of why and how
    * Create our simple application
    * Install ExternalSecret operator helm-chart
3. Learn about argo
    * Install argo
    * Deploy our simple application through argo
4. Learn how we do it in Make
5. If time left:
    * Reverse Proxy and how to use it
        * traefik
        * cloudflare
    * Serverles locally
        * install and configure KNative
        * Deploy a hello-world serverles app
        * ArgoNize this app
        * Install VisualStudio Code server serverless
        * set up all needed ingresses to get a server of the dream
