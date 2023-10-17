# just-one-yaml-deployment

this is a prototype how to deploy apps with just one yaml

# current structure

## apps

in each sub directory is its own app with just one deployment yaml with all its deployment information in it
e.g.
 - my-nginx-website/deployit.yaml
 - my-java-service/deployit.yaml

## argocd-config

we will use argocd to deploy each app so put the necessary applications or applicationset definitions in this folder. those yamls will just get synced to the argocd namespace

## awesome-app-chart

this is where our awesome flexible app helm chart is defined which will be used in our applicationset together with all  apps/<app>/deployit.yaml values files

## platform-services

if we we need some other K8s manifests for deploying kubevela or crossplane things ... don't really know :)

# installation

1. install argocd

2. apply argocd-config manifests

`kubectl apply -f argocd-config/* `
