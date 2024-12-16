# -k8s-gateway-api-service-mesh


kind create cluster  --config kind-config.yaml

kubectl create namespace gateway-api-demo
kubectl config set-context --current --namespace=gateway-api-demo


kubectl apply -k "github.com/kubernetes-sigs/gateway-api/config/crd?ref=v0.8.0"


Set up Istio Service Mesh

brew install istioctl
istioctl install --set profile=default
kubectl label namespace gateway-api-demo istio-injection=enabled