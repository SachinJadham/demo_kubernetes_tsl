# demo_kubernetes_tls_SSL : https
  Install and run ingress controller and controller services 

kubectl run nginx --image=nginx 

kubectl expose deployment nginx --type="NodePort" --port 80  

Reserve a global static IP named demostaticip 

Kubectl apply –f  ingress_staticip_cert_nohost.yml 

Ingress linked to certificate must be running  to provision the certificate. 

Configure clouds DNS nameserver [DNSSEC- ON]  : point domain name to static IP; configure namerserver in registrar (freenom.com) 

 

You must wait for the DNS records you configured in above step to propagate before continuing. 

 

Kubectl apply –f certificate_res.yaml   

Kubectl describe managedceritificate example-nginx-certificate : check status -> provisioning in beginning  ; This may take up to 30 minutes. 
