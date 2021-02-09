


### 01-Creating a Kubernetes service account in the kubesystem namespace:

```
kubectl apply -f https://raw.githubusercontent.com/kubernetes-sigs/aws-alb-ingress-controller/master/docs/examples/rbac-role.yaml

kubectl get sa -n kube-system

kubectl describe sa alb-ingress-controller -n kube-system


```


### 02-Creating IAM Policy for ALB Ingress Controller:
This IAM policy will allow ALB Ingress Controller pod to make calls to AWS APIs

```
# Create IAM Policy
aws iam create-policy \
    --policy-name ALBIngressControllerIAMPolicy \
    --policy-document https://raw.githubusercontent.com/kubernetes-sigs/aws-alb-ingress-controller/master/docs/examples/iam-policy.json
```

we will need the policy ARN when we create the IAM Role in the next step.

### 03-Creating IAM role for the ALB Ingress Controller and attach the role to the service account:

This will create an AWS IAM role and attach it to Kubernetes service account
```
eksctl create iamserviceaccount \
    --region us-east-1 \
    --name alb-ingress-controller \
    --namespace kube-system \
    --cluster ntier \
    --attach-policy-arn arn:aws:iam::773910315572:policy/ALBIngressControllerIAMPolicy \
    --override-existing-serviceaccounts \
    --approve
    
    
eksctl  get iamserviceaccount --cluster ntier
kubectl describe sa alb-ingress-controller -n kube-system
```

### 04-Deploying the pods, services and the ALB:

```
kubectl apply -f kube-manifests/

```


