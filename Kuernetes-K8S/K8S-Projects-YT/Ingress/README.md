````
# kubectl create namespace ingress-nginx
# kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.2.1/deploy/static/provider/cloud/deploy.yaml 
# we deployed ingress controller it created jobs, pods, services and all components
````

````
# kubectl get all -n ingress-nginx
# kubectl get pods
# kubectl get deploy
# kubectl get svc
# kubectl apply -f dep-one.yaml
# kubectl apply -f dep-two.yaml
# kubectl get pods
# kubectl get deploy
# kubectl get svc
# kubectl apply -f ingress-resource.yaml
# kubectl get ingress (To get Address) :- ip address past in chrome. 
# <address ip> :- To get nginx webpage 
# <address ip>/nginx :- To get nginx webpage 
# <address ip>/httpd :- To get httpd webpage.
# kubectl grt service -n ingress-nginx 
````
