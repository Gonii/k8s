kind create cluster --config kind-config.yaml
kubectl label node/kind-worker2 "ingress-ready=true"
kubectl apply -f ingress-nginx-deploy.yaml
