<h4>before install </h4>

```bash
kubectl get nodes
```
<h4>Step 2: Install Metrics Server using official YAML</h4>
```bash
kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml

```
<h4>check : metrics-server Deployment (in kube-system namespace) Related RBAC roles and services.</h4>

Step 3: (Optional but important) — Add args if using EC2 / custom cluster
```bash
kubectl edit deployment metrics-server -n kube-system
```
Then, under spec.template.spec.containers.args, add these lines:
```bash
args:
  - --kubelet-insecure-tls
  - --kubelet-preferred-address-types=InternalIP
```
Then restart the pod:
```bash
kubectl rollout restart deployment metrics-server -n kube-system
```
Step 4: Verify installation
```bash
kubectl get pods -n kube-system | grep metrics
```
Step 5: Test metrics API

```bash
kubectl top nodes
kubectl top pods --all-namespaces
```
