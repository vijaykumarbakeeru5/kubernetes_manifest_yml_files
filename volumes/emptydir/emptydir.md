---
apiVersion: v1
kind: Pod
metadata:
  name: myvolemptydir
spec:
  containers:
  - name: c1-write
    image: centos:7
    command: ["/bin/bash", "-c", "sleep 15000"]
    volumeMounts:
    - name: xchange
      mountPath: "Vijay/xchange"
  - name: c2-read
    image: centos:7
    command: ["/bin/bash", "-c", "sleep 10000"]
    volumeMounts:
    - name: xchange
      mountPath: "Vijay/mydata"
  volumes:
  - name: xchange
    emptyDir: {}
```

```
kubectl apply -f emptydir.yml
```
