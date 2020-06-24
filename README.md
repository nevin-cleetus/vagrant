

kubectl create namespace monitoring


kubectl apply -f cluster-role.yml 

kubectl apply -f  config-map.yml

kubectl apply -f prometheus-deploy.yml

