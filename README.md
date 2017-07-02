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

- Checks logs

kubectl logs replicas-3144326441-pmhtj

kubectl logs --tail=10 replicas-3144326441-pmhtj 

kubectl logs --since=24h replicas-3144326441-pmht

kubectl logs -f replicas-3144326441-pmht



