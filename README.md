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

