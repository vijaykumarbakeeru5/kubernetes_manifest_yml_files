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
