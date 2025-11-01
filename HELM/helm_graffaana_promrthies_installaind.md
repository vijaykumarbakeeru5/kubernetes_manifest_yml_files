Helm Installation
```bash
# helm
```
```bash
curl -fsSl -o get_helm.sh https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3
```
```bash
chmod 700 get_helm.sh
```
```bash
./get_helm.sh # install sh script
```
```bash
helm
```
check do we have metrics server on the cluster
```bash
kubectl top pods
kubectl top nodes
```
# check helm repos
```bash
helm repo ls
```

Install Prometheus & Grafana In K8S Cluster using HELM
Add the latest helm repository in Kubernetes
```bash
helm repo add stable https://charts.helm.sh/stable
```
Add prometheus repo to helm
```bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
```
Update Helm Repo
```bash
helm repo update
```
install prometheus
```bash
helm install stable prometheus-community/kube-prometheus-stack
```
Get all pods
``bash
kubectl get pods
```
Node: You should see prometheus pods running
# Check the services
```bash
kubectl get svc
```
# By default prometheus and grafana services are available within the cluster as ClusterIP, to access them outside lets change it to NodePort / LoadBalancer.

# Edit Prometheus Service & change service type to LoadBalancer then save and close that file
```bash
kubectl edit svc stable-kube-prometheus-sta-prometheus
```
# Now edit the grafana service & change service type to LoadBalancer then save and close that file
```bash
kubectl edit svc stable-grafana
```
# Verify the service if changed to LoadBalancer
```bash
kubectl get svc
```
password:
```bash
kubectl --namespace default get secrets stable-grafana -o jsonpath="{.data.admin-password}" | base64 -d ; echo
```
