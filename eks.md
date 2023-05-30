curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp
sudo mv /tmp/eksctl /usr/local/bin
eksctl version
aws configure set region ap-northeast-2
cd .ssh
ssh-keygen

aws ec2 import-key-pair --key-name "workernode key" --public-key-material file://~/.ssh/id_rsa.pub

eksctl create cluster --name mission-cluster --version 1.22 --region ap-northeast-2 --nodegroup-name mission-wn --node-type t3.medium --nodes 1 --nodes-min 1 --nodes-max 1 --ssh-access --ssh-public-key "workernode key" --managed

kubectl get node

kubectl apply -f nginx-deployment.yaml

nginx-deployment.yaml
```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-nginx
spec:
  selector:
    matchLabels:
      run: my-nginx
  replicas: 2
  template:
    metadata:
      labels:
        run: my-nginx
    spec:
      containers:
      - name: my-nginx
        image: nginx
        ports:
        - containerPort: 80
```
kubectl apply -f nginx-service.yaml
```
apiVersion: v1
kind: Service
metadata:
  name: my-nginx
  labels:
    run: my-nginx
spec:
  ports:
  - port: 80
    protocol: TCP
  selector:
    run: my-nginx
  type: LoadBalancer
```
kubectl get pod
kubectl get service
kubectl delete -f nginx-service.yaml
kubectl delete -f nginx-deployment.yaml
eksctl delete cluster --region ap-northeast-2 --name=mission-cluster

---

```
apiVersion
: apps/v1
kind: Deployment
metadata:
name:
elasticsearch
labels:
app:
elasticsearch
spec:
replicas: 1
selector:
matchLabels
app:
elasticsearch
template:
metadata:
labels:
app:
elasticsearch
spec:
containers:
-
name: elasticsearch
image: elastic/elasticsearch:6.4.0
env:
-
name: discovery.type
value: "single
node"
ports:
-
containerPort : 9200
-
containerPort : 9300
---
apiVersion
: v1
kind: Service
metadata:
labels:
app:
elasticsearch
name:
elasticsearch svc
namespace: default
spec:
```
