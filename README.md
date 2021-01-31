# Kubernetes



### 01- Create EKS Cluster using eksctl:

```
eksctl create cluster --name=node-server \
                      --region=us-east-1 \
                      --zones=us-east-1a,us-east-1b \
                      --without-nodegroup 
```
Getting the cluster list:

```
eksctl get clusters
```
### 02- Create & Associate IAM OIDC Provider for the EKS Cluster

```
eksctl utils associate-iam-oidc-provider \
    --region us-east-1 \
    --cluster node-server \
    --approve
```




Interact With a Pod:

- kubectl get po : Get pod name
- kubectl logs POD_NAME: dump pod logs
- kubectl logs -f POD_NAME: -f option to stream pod logs
  
Connection into the POD container:

- kubectl exec -it POD_NAME -- /bin/bash

Get YAML output of POD and Service:

- kubectl get pod POD_NAME -o yaml
- kubectl get service SERVICE_NAME -o yaml
