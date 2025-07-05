## Manifest File in YAML language to create pod:
``` bash
vi pod.yaml
apiVersion: v1
kind: Pod
metadata:
  name: mypod
spec:
  containers:
    - name: c00
      image: nginx
```
#### Command to apply pod.yaml
``` bash
 kubectl apply -f pod.yaml
```
#### Commands to check status and details of pod
``` bash
kubectl get pods
kubectl get pods -o wide
kubectl describe pods
```
#### Commands to delete pod
``` bash
kubectl delete pod mypod
or
kubectl delete -f pod.yaml
```
