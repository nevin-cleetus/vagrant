

sudo yum install git

mkdir k8repo
cd k8repo

git clone https://github.com/nevin-cleetus/vagrant.git

cd vagrant


Prometheus & Grafana on Kubernetes Environment
==============================================


kubectl create namespace monitoring

kubectl apply -f cluster-role.yml 

kubectl apply -f  config-map.yml

kubectl apply -f prometheus-deploy.yml


kubectl get svc -n monitoring
The result should contain the prometheus service running as NodePort service 


kubectl apply -f grafana-configmap.yml

kubectl apply -f grafana-deployment.yml 

kubectl apply -f grafana-service.yml 

kubectl get svc -n monitoring
The result should contain the grafana service running as NodePort service 

Now we should be able to access the service by assessing the NodePorts of the services

For Exp -  
            http://172.42.42.100:30000/     [The Port 30000 is the NodePort for the Prometheus service. Use the Port specific for your service]
           
            http://172.42.42.100:32000/     [The Port 32000 is the NodePort for the grafana service]
            
            
Prometheus & Grafana on Kubernetes Docker 
=========================================

You may rename the Vagrant_docker to Vagrant (The default Vagrant file in the repo to Vagrant_Kubernetes). 

Run the vagrant command

vagrant up 


This should create a VM with docker installed in it.  You may then install prometheus and Grafana as either docker container or install as normal installation.




            
            

           
