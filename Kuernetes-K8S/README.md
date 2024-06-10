# Commands to cteate namespace
```
# aws configure      : To configure with aws account
# aws eks update-kubeconfig --name myk8scluster --region=ap-south-1    : To add and contact with aws cluster
# kubectl get nodes   : To list existing nodes/objects in the cluster
# kubectl get namespace  : To list namespaces in the cluster
# kubectl get pods    : To list podes in the cluster
# kubectl get pods --namespace <namespace name>   : To check podsin Namespace
# kubectl delete namespace <ns name> : To delete namespace 
```

# To create and excute namespace.yaml file
```
# kubectl cteate namespace <namespace name>       : To create new namespace
# kubectl get namespace  : To show new and all namespaces
# kubectl api-resources  : To display all info about nodes/objects
# kubectl create -f namespace.yaml  : To create namespace
# kubectl get namespace  : To List all namespaces
# kubectl delete namespace <ns name> : To delete namespace 
```

# To create and excute pod.yaml file
```
# kubectl create -f pod.yaml  : To create pod
# kubectl get namespace  : To List all namespaces
# kubectl decribe pod my-pod -n devops  : To inspect pod (n=namespace)
# kubectl get pods -namespace <namespace name>   : To check podsin Namespace
# kubectl delete pod <podname> -n devops  : To delete pod
```

# To create and excute replicaset.yaml file (rs=replicaset)
```
# kubectl create -f replicaset.yaml  : To create replicaset
# kubectl get replicaset  : To List all replicaset
# kubectl get pods    : To list podes in the cluster
# kubectl decribe rs/my-replicaset   : To show all info about replicaset
# kubectl delete pod <my-replicaset-29M52>  : To delete pod
# Deleted pod will create again due to replicaset you can increase and decrease replicaset in code
# kubectl apply -f replicaset.yaml  : To update configure is added
# kubectl delete rs my-replicaset   : To delete replicasets and pods. pods will not create again
```

# To create and excute deployment.yaml file (rs=replicaset)
```
# kubectl create -f deployment.yaml  : To create deployment
# kubectl get deploy : To List all deployments
# kubectl get rs    : To list and check replicasets
# kubectl get pods    : To list podes in the rs and deployment
# kubectl decribe pod <podname>   : To show all info about pod image

# kubectl get image deploy/my-deploy myapp-helloworld:2.0 : This command is used to update pods and deploy using CLI
# kubectl rollout undo deploy/my-deploy : To get back to previous version.
```

# To create and excute service.yaml file
```
# kubectl create -f service.yaml  : To create service
# kubectl get service : To List all service Name,Type, Cluster IP & External IP
#open a new tab and enter external IP to check working or not (with :80 if not work).
```
