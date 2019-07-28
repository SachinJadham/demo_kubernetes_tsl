# demo_kubernetes_tsl
  1. Make sure you have ingress controller running  on your cluster:  kubectl get po --all-namespaces 
      a. You should see an ingress controller running as a pod 
  2. If Ingress controller is not installed:- 
      a. kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/master/deploy/static/mandatory.yaml 
      b. kubectl get po --all-namespaces -> now you can see a nginx ingress controller pod running 
      c. Create Ingress service: kubectl apply -f       https://raw.githubusercontent.com/kubernetes/ingressnginx/master/deploy/static/provider/cloud-generic.yaml 
      d. kubectl get all --all-namespaces 
   3. We need to create Ingress resources which the Ingress controller consumes. Before that: we deploy our demo app. 
      a. kubectl run nginx --image=nginx 
      b. kubectl expose deployment nginx --port 80 
      c. Create ingress resource:- 
      d. Resource definition file: ingress.yml file in this repo: kubectl apply ingress.yml   
      e. kubectl get ingress -> you should see the ingress resource and the also the assigned IP
      f. to test this: remove the host name from the ingress.yml file and apply again and then open the assigned ingress IP in a new tab
