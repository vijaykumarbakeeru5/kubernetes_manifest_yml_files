get the metric server by the helm , chagge false and true at last

```bash
helm upgrade --install custom-metrics-server metrics-server/metrics-server \
--namespace kube-system \
--set "args={--kubelet-insecure-tls,--kubelet-preferred-address-types=InternalIP}" \
--set apiService.create=true
```
