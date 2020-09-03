kubectl run ghost-pod --image ghost --restart Never --port 2368

kubectl get pods

kubectl describe pod ghost-pod 

kubectl logs ghost-pod

kubectl exec -it ghost-pod -- /bin/sh 

kubectl port-forward po/ghost-pod 2368:2368

cd k8s

kubectl run webinar-demo --image nj93/webinar-demo:v1  --port 8080 --dry-run -o yaml > deployment.yaml
kubectl apply -f deployment.yaml 

kubectl expose deploy/webinar-demo --port 80 --target-port 8080 --type LoadBalancer --dry-run -o yaml

kubectl create cm config-json --from-file=../config/config.json --dry-run -o yaml > config.yaml

kubectl autoscale deploy webinar-demo --min 1 --max 5 --cpu-percent=70 --dry-run -o yaml

kubectl get all