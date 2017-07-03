# kubernetes- commands

- To see the running pod

kubectl describe pod nginx ot kubectl describe pods

- To start a busybox container

kubectl run busybox --image=busybox --restart=Never --tty -i --generator=run-pod/v1

- To delete a pod

kubcetl delete pod busybox

- Port forwarding to pod

kubectl port-forward nginx 8000:80 &
verify

wget -qO- http://localhost:8000

- To list a pod with label

kubectl describe pod -l app=nginx2

- Apply update to only one deployment

kubectl apply -f nginx-deployment-dev-update.yaml 

- To see the service

kubectl get service 

 kubectl describe service nginx-service

- Create replica from commandline

kubectl run mysample --image=latest123/apache

kubectl run replicas --image=latest123/apache --replicas=2 --labels=app=apache

- Connect to a container

kubectl exec my_cont -i -t -- /bin/bash

- Run a command that displays the pod's container /var/www/html/index.html

kubectl exec mypod -i -t -- cat /var/www/html/index.html

- Checks logs

kubectl logs replicas-3144326441-pmhtj

kubectl logs --tail=10 replicas-3144326441-pmhtj 

kubectl logs --since=24h replicas-3144326441-pmht

kubectl logs -f replicas-3144326441-pmht

- Autoscaling

Kubectl autoscale deployment mypodname —min2 —max=6

- If you want to make changes to the above

Kubectl scale —current-replicas=2 —replicas=4 deployment/mypodname

Scale down (you can only scale down to the initial min)

Kubectl scale —current-replicas=4 —replicas=2 deployment/mypodname

