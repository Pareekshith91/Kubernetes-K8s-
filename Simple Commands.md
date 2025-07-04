# Kubernetes-K8s
## Simple Commands:
``` bash
root@ip-172-31-4-255:~# kubectl get nodes
NAME               STATUS   ROLES           AGE     VERSION
ip-172-31-10-147   Ready    <none>          2m6s    v1.30.14
ip-172-31-4-255    Ready    control-plane   2m30s   v1.30.14
root@ip-172-31-4-255:~# kubectl run pod-xyz --image=nginx
pod/pod-xyz created
root@ip-172-31-4-255:~# kubectl get pods
NAME      READY   STATUS    RESTARTS   AGE
pod-xyz   1/1     Running   0          55s
root@ip-172-31-4-255:~# kubectl get pods -o wide
NAME      READY   STATUS    RESTARTS   AGE   IP          NODE               NOMINATED NODE   READINESS GATES
pod-xyz   1/1     Running   0          66s   10.40.0.3   ip-172-31-10-147   <none>           <none>
root@ip-172-31-4-255:~# kubectl describe pod pod-xyz
Name:             pod-xyz
Namespace:        default
Priority:         0
Service Account:  default
Node:             ip-172-31-10-147/172.31.10.147
Start Time:       Fri, 04 Jul 2025 16:00:50 +0000
Labels:           run=pod-xyz
Annotations:      <none>
Status:           Running
IP:               10.40.0.3
IPs:
  IP:  10.40.0.3
Containers:
  pod-xyz:
    Container ID:   containerd://6482a158594ae176897d3e1681ac2ecb6ef7c30d5116b86add75b21c32963c32
    Image:          nginx
    Image ID:       docker.io/library/nginx@sha256:93230cd54060f497430c7a120e2347894846a81b6a5dd2110f7362c5423b4abc
    Port:           <none>
    Host Port:      <none>
    State:          Running
      Started:      Fri, 04 Jul 2025 16:00:55 +0000
    Ready:          True
    Restart Count:  0
    Environment:    <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-mbnjf (ro)
Conditions:
  Type                        Status
  PodReadyToStartContainers   True
  Initialized                 True
  Ready                       True
  ContainersReady             True
  PodScheduled                True
Volumes:
  kube-api-access-mbnjf:
    Type:                    Projected (a volume that contains injected data from multiple sources)
    TokenExpirationSeconds:  3607
    ConfigMapName:           kube-root-ca.crt
    ConfigMapOptional:       <nil>
    DownwardAPI:             true
QoS Class:                   BestEffort
Node-Selectors:              <none>
Tolerations:                 node.kubernetes.io/not-ready:NoExecute op=Exists for 300s
                             node.kubernetes.io/unreachable:NoExecute op=Exists for 300s
Events:
  Type    Reason     Age   From               Message
  ----    ------     ----  ----               -------
  Normal  Scheduled  94s   default-scheduler  Successfully assigned default/pod-xyz to ip-172-31-10-147
  Normal  Pulling    93s   kubelet            Pulling image "nginx"
  Normal  Pulled     89s   kubelet            Successfully pulled image "nginx" in 4.075s (4.075s including waiting). Image size: 72225394 bytes.
  Normal  Created    89s   kubelet            Created container: pod-xyz
  Normal  Started    89s   kubelet            Started container pod-xyz
root@ip-172-31-4-255:~# kubectl delete pod pod-xyz
pod "pod-xyz" deleted
root@ip-172-31-4-255:~#
```
