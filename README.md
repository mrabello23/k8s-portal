# k8s-portal

Primeiro portal com K8S

## Required

- docker desktop
- kubernetes enabled
- open ports 30000 and 30001

## Execute

- execute docker and kubernetes
- open root folder in terminal
- apply pods, services and configMaps declarations
- open portal at: http://localhost:30000
- open administrative portal at: http://localhost:30001
- user: admin / pass: admin

## Commands

- Access Pods:
  - `kubectl exec -it NAME-OF-POD -- bash`
- Services:
  - `kubectl apply -f ./Services/svc-portal-noticias.yaml`
  - `kubectl apply -f ./Services/svc-sistema-noticias.yaml`
  - `kubectl apply -f ./Services/svc-db-noticias.yaml`
- Config Maps:
  - `kubectl apply -f ./ConfigMaps/portal-configmap.yaml`
  - `kubectl apply -f ./ConfigMaps/sistema-configmap.yaml`
  - `kubectl apply -f ./ConfigMaps/db-configmap.yaml`
- Deployment:
  - `kubectl apply -f ./Deployments/portal-noticias-deployment.yaml`
  - `kubectl apply -f ./Deployments/db-noticias-deployment.yaml`
- Stateful Set:
  - `kubectl apply -f ./StatefulSet/sistema-noticias-statefulset.yaml`
- List and details:
  - `kubectl get all`
  - `kubectl get pods -o wide`
  - `kubectl get svc`
  - `kubectl get configmap`
  - `kubectl get deployments`
  - `kubectl get statefulset`
  - `kubectl describe [pod/svc/configmap/deployment] NAME-OF-RESOURCE`

## Cleanup environment

- Remove Deployment: `kubectl delete deployment --all`
- Remove services: `kubectl delete svc --all`
- Remove stateful set: `kubectl delete statefulset --all`
- Remove configMaps: `kubectl delete configMaps --all`
- Remove pods: `kubectl delete pods --all`
