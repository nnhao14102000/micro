# Microservice .NET5

## Docker command
`docker build -t hao14102000/commandservice .`  
`docker push hao14102000/commandservice`  

`docker build -t hao14102000/platformservice .`  
`docker push hao14102000/platformservice`  

## Kubernetes command
`kubectl apply -f .\commands-depl.yaml`  
`kubectl apply -f .\platforms-depl.yaml`  
`kubectl apply -f .\ingress-srv.yaml`  
`kubectl apply -f .\platforms-np-srv.yaml`  
- Ingress nginx:  
`kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.0.1/deploy/static/provider/cloud/deploy.yaml`

`kubectl get pods`  
`kubectl get services`  
`kubectl get deployments`  
`kubectl get namespace`  
`kubectl get deployments --namespace=ingress-nginx`  
`kubectl get pods --namespace=ingress-nginx`  
`kubectl get service --namespace=ingress-nginx`  


- SQL  
`kubectl get storageclass`  
`kubectl apply -f .\local-pvc.yaml`  
`kubectl get pvc`  
`kubectl create secret generic mssql --from-literal=SA_PASSWORD="Pa55w0rd!"`  
`kubectl apply -f .\mssql-plat-depl.yaml`  
`kubectl rollout restart deployment platforms-depl` (restart a deployment)  
`kubectl delete deployment platforms-depl` (delete deployment if it error, after delete, rebuilt, push to docker, and deploy again)

- RabbitMQ   
`kubectl apply -f .\rabbitmq-depl.yaml`  