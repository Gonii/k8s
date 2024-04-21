kubectl apply -f ingress-nginx-deploy.yaml
kubectl label node/kind-worker2 "ingress-ready=true"