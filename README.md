# Azure_AKS

1. Goto `portal.azure.com` open the AKS


2. Click on Create Kubernetes cluster -> 

    Create a new Resource group 
    
    Kubernetes cluster name - `three-tier-pavan`
    
    Availability Zone - `Zone1`
    
    Click on Review + Create

![aks](https://github.com/Pavan-1997/Azure_AKS/assets/32020205/bbaf8d05-671e-4779-9ed3-dbb9bc694efb)


3. Open the terminal

```
az login
```
```
az account set --subscription <subscription-id>
```
```
az aks get-credentials --resource-group <resource-group-name> --name <cluster-name>
```
```
kubectl config current-context
```

4. Clone the current repo Repo 

```
cd three-tier-architecture-demo/AKS/helm
```
```
kubectl create ns robot-shop
```
```
helm install robot-shop --namespace robot-shop .
```
```
kubectl create ns robot-shop
```
![get-pods](https://github.com/Pavan-1997/Azure_AKS/assets/32020205/119e9c01-9842-4dd7-82a9-1885959afd60)


5. Access app from the LB created

![app-lb](https://github.com/Pavan-1997/Azure_AKS/assets/32020205/163b58ef-5041-4c7c-944f-b5a6e6557a2f)


6. Enable Ingress Controller 

In the created Kubernetes cluster -> Goto Networking on the left -> Enable the ingress controller -> Click on Apply 

```
kubectl apply -f ingress.yaml -n robot-shop
```
```
kubectl get pods -n kube-system
```
```
kubectl get ing -n robot-shop
```

