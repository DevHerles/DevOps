#### `❯ kubectl get pods`
```bash
NAME                                     READY   STATUS    RESTARTS   AGE
hello-world-deployment-d6d974dcc-q8gdp   1/1     Running   0          108m
```

#### `❯ kubectl get pods -o wide`
```bash
NAME                                     READY   STATUS    RESTARTS   AGE    IP            NODE       NOMINATED NODE   READINESS GATES
hello-world-deployment-d6d974dcc-q8gdp   1/1     Running   0          110m   10.244.0.34   minikube   <none>           <none>
```

#### `❯ pwd`
```bash
/home/herles/asf/devherles/DevOps
```

#### `❯ k gett pods`
```bash
```

#### `❯ kubectl get pods`
```bash
NAME                                     READY   STATUS    RESTARTS   AGE
hello-world-deployment-d6d974dcc-q8gdp   1/1     Running   0          4h54m
```

#### `❯ kubectl expose deployment hello-world-deployment --port=3000`
```bash
service/hello-world-deployment exposed
```

#### `❯ kubectl get svc`
```bash
NAME                     TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)    AGE
fileserver               ClusterIP   10.106.215.205   <none>        5005/TCP   29h
hello-world-deployment   ClusterIP   10.97.86.48      <none>        3000/TCP   28s
kubernetes               ClusterIP   10.96.0.1        <none>        443/TCP    7d22h
```

#### `❯ minikube ip`
```bash
192.168.49.2
```

#### `❯ minikube -h`
```bash
minikube provisions and manages local Kubernetes clusters optimized for development workflows.

Basic Commands:
  start            Starts a local Kubernetes cluster
  status           Gets the status of a local Kubernetes cluster
  stop             Stops a running local Kubernetes cluster
  delete           Deletes a local Kubernetes cluster
  dashboard        Access the Kubernetes dashboard running within the minikube cluster
  pause            pause Kubernetes
  unpause          unpause Kubernetes

Images Commands:
  docker-env       Provides instructions to point your terminal's docker-cli to the Docker Engine inside minikube. (Useful for building docker images directly inside minikube)
  podman-env       Configure environment to use minikube's Podman service
  cache            Manage cache for images
  image            Manage images

Configuration and Management Commands:
  addons           Enable or disable a minikube addon
  config           Modify persistent configuration values
  profile          Get or list the current profiles (clusters)
  update-context   Update kubeconfig in case of an IP or port change

Networking and Connectivity Commands:
  service          Returns a URL to connect to a service
  tunnel           Connect to LoadBalancer services

Advanced Commands:
  mount            Mounts the specified directory into minikube
  ssh              Log into the minikube environment (for debugging)
  kubectl          Run a kubectl binary matching the cluster version
  node             Add, remove, or list additional nodes
  cp               Copy the specified file into minikube

Troubleshooting Commands:
  ssh-key          Retrieve the ssh identity key path of the specified node
  ssh-host         Retrieve the ssh host key of the specified node
  ip               Retrieves the IP address of the specified node
  logs             Returns logs to debug a local Kubernetes cluster
  update-check     Print current and latest version number
  version          Print the version of minikube
  options          Show a list of global command-line options (applies to all commands).

Other Commands:
  completion       Generate command completion for a shell
  license          Outputs the licenses of dependencies to a directory

Use "minikube <command> --help" for more information about a given command.
```

#### `❯ minikube ssh`
```bash
[?2004h]0;docker@minikube: ~docker@minikube:~$ curl [7m192.168.49.2[27m192.168.49.2:3000
[?2004l
curl: (7) Failed to connect to 192.168.49.2 port 3000 after 0 ms: Connection refused
[?2004h]0;docker@minikube: ~docker@minikube:~$ curl 192.168.49.2:3000[1P[1@5
[?2004l
curl: (7) Failed to connect to 192.168.49.2 port 5000 after 0 ms: Connection refused
[?2004h]0;docker@minikube: ~docker@minikube:~$ curl 192.168.49.2:5000     
[?2004l
<html>

<head><title>404 Not Found</title></head>

<body>

<center><h1>404 Not Found</h1></center>

<hr><center>nginx</center>

</body>

</html>

[?2004h]0;docker@minikube: ~docker@minikube:~$ curl [7m10.97.86.48[27m10.97.86.48:3000
[?2004l
curl: (7) Failed to connect to 10.97.86.48 port 3000 after 0 ms: Connection refused
[?2004h]0;docker@minikube: ~docker@minikube:~$ curl 10.97.86.48:3000[1P[1@5
[?2004l

^C
[?2004h]0;docker@minikube: ~docker@minikube:~$ curl 10.97.86.48:5000     
[?2004l
^C
[?2004h]0;docker@minikube: ~docker@minikube:~$ curl 10.97.86.48:5000
[?2004l
^C
[?2004h]0;docker@minikube: ~docker@minikube:~$ curl 10.97.86.48:50007[1P[1P[1@1[1@0[1@3.86.48[1P[1P[1P[1P[1P[1P[1P00[K0[K[K186, .155
[?2004l
<html><body><h1>Hostname: hello-world-deployment-d6d974dcc-q8gdp</h1><h1>IP Address: 10.244.0.34</h1><p>Hello, World!</p></body></html>[?2004h]0;docker@minikube: ~docker@minikube:~$ 
[?2004l
[?2004h]0;docker@minikube: ~docker@minikube:~$ curl 10.103.186.155
[?2004l
^C
[?2004h]0;docker@minikube: ~docker@minikube:~$ curl 10.103.186.155:8088
[?2004l
^C
[?2004h]0;docker@minikube: ~docker@minikube:~$ [Kcurl 10.107.242.158:8088
[?2004l
<html><body><h1>Hostname: hello-world-deployment-d6d974dcc-q8gdp</h1><h1>IP Address: 10.244.0.34</h1><p>Hello, World!</p></body></html>[?2004h]0;docker@minikube: ~docker@minikube:~$ [K[?2004l

logout
```

#### `❯ kubectl delete svc hello-world-deployment`
```bash
service "hello-world-deployment" deleted
```

#### `❯ kubect expose deployment hello-world-deployment --port=8088 --target-port=80`
```bash
```

#### `❯ kubectl expose deployment hello-world-deploymeny --port=8088 --target-port=80`
```bash
```

#### `❯ kubectl expose deployment hello-world-deployment --port=8088 --target-port=80`
```bash
service/hello-world-deployment exposed
```

#### `❯ minikube ssh`
```bash
[?2004h]0;docker@minikube: ~docker@minikube:~$ [?2004l

logout
```

#### `❯ kubectl get svc`
```bash
NAME                     TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)    AGE
fileserver               ClusterIP   10.106.215.205   <none>        5005/TCP   29h
hello-world-deployment   ClusterIP   10.97.167.51     <none>        8088/TCP   23s
kubernetes               ClusterIP   10.96.0.1        <none>        443/TCP    7d23h
```

#### `❯ minikube ssh`
```bash
[?2004h]0;docker@minikube: ~docker@minikube:~$ curl 10.97.167.51:8088
[?2004l
<html><body><h1>Hostname: hello-world-deployment-d6d974dcc-q8gdp</h1><h1>IP Address: 10.244.0.34</h1><p>Hello, World!</p></body></html>[?2004h]0;docker@minikube: ~docker@minikube:~$ 
[?2004l
[?2004h]0;docker@minikube: ~docker@minikube:~$ [?2004l

logout
```

#### `❯ kubectl scale deployment hello-world-deployment --replicas=4`
```bash
deployment.apps/hello-world-deployment scaled
```

#### `❯ kubectl get pods`
```bash
NAME                                     READY   STATUS              RESTARTS   AGE
hello-world-deployment-d6d974dcc-4c52v   0/1     ContainerCreating   0          7s
hello-world-deployment-d6d974dcc-b5g8s   0/1     ContainerCreating   0          7s
hello-world-deployment-d6d974dcc-q8gdp   1/1     Running             0          5h20m
hello-world-deployment-d6d974dcc-q8zfg   0/1     ContainerCreating   0          7s
```

#### `❯ kubectl get pods`
```bash
NAME                                     READY   STATUS    RESTARTS   AGE
hello-world-deployment-d6d974dcc-4c52v   1/1     Running   0          22s
hello-world-deployment-d6d974dcc-b5g8s   1/1     Running   0          22s
hello-world-deployment-d6d974dcc-q8gdp   1/1     Running   0          5h21m
hello-world-deployment-d6d974dcc-q8zfg   1/1     Running   0          22s
```

#### `❯ minikube ssh`
```bash
[?2004h]0;docker@minikube: ~docker@minikube:~$ curlo  10.107.242.158:8088
[?2004l
^C
[?2004h]0;docker@minikube: ~docker@minikube:~$ [Kcurl 10.97.167.51:8088
[?2004l
<html><body><h1>Hostname: hello-world-deployment-d6d974dcc-b5g8s</h1><h1>IP Address: 10.244.0.35</h1><p>Hello, World!</p></body></html>[?2004h]0;docker@minikube: ~docker@minikube:~$ 
[?2004l
[?2004h]0;docker@minikube: ~docker@minikube:~$ curl 10.97.167.51:8088
[?2004l
<html><body><h1>Hostname: hello-world-deployment-d6d974dcc-4c52v</h1><h1>IP Address: 10.244.0.36</h1><p>Hello, World!</p></body></html>[?2004h]0;docker@minikube: ~docker@minikube:~$ curl 10.97.167.51:8088
[?2004l
<html><body><h1>Hostname: hello-world-deployment-d6d974dcc-q8gdp</h1><h1>IP Address: 10.244.0.34</h1><p>Hello, World!</p></body></html>[?2004h]0;docker@minikube: ~docker@minikube:~$ [?2004l

logout
```

#### `❯ cd /home/herles/asf/devherles/hello_world`
```bash
```

#### `❯ pwd`
```bash
/home/herles/asf/devherles/DevOps
```

#### `❯ cd ..`
```bash
```

#### `❯ pwd`
```bash
/home/herles/asf/devherles/DevOps
```

#### `❯ kubectl get all`
```bash
NAME                                         READY   STATUS    RESTARTS   AGE
pod/hello-world-deployment-d6d974dcc-4c52v   1/1     Running   0          14m
pod/hello-world-deployment-d6d974dcc-b5g8s   1/1     Running   0          14m
pod/hello-world-deployment-d6d974dcc-q8gdp   1/1     Running   0          5h34m
pod/hello-world-deployment-d6d974dcc-q8zfg   1/1     Running   0          14m

NAME                             TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)    AGE
service/fileserver               ClusterIP   10.106.215.205   <none>        5005/TCP   29h
service/hello-world-deployment   ClusterIP   10.97.167.51     <none>        8088/TCP   22m
service/kubernetes               ClusterIP   10.96.0.1        <none>        443/TCP    7d23h

NAME                                     READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/hello-world-deployment   4/4     4            4           5h34m

NAME                                               DESIRED   CURRENT   READY   AGE
replicaset.apps/hello-world-deployment-d6d974dcc   4         4         4       5h34m
```

#### `❯ kubectl delete deployment hello-world-deployment`
```bash
deployment.apps "hello-world-deployment" deleted
```

#### `❯ kubectl get all`
```bash
NAME                                         READY   STATUS        RESTARTS   AGE
pod/hello-world-deployment-d6d974dcc-b5g8s   0/1     Terminating   0          15m

NAME                             TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)    AGE
service/fileserver               ClusterIP   10.106.215.205   <none>        5005/TCP   29h
service/hello-world-deployment   ClusterIP   10.97.167.51     <none>        8088/TCP   23m
service/kubernetes               ClusterIP   10.96.0.1        <none>        443/TCP    7d23h
```

#### `❯ kubectl get all`
```bash
NAME                             TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)    AGE
service/fileserver               ClusterIP   10.106.215.205   <none>        5005/TCP   29h
service/hello-world-deployment   ClusterIP   10.97.167.51     <none>        8088/TCP   23m
service/kubernetes               ClusterIP   10.96.0.1        <none>        443/TCP    7d23h
```

#### `❯ kubectl delete svc hello-world-deployment`
```bash
service "hello-world-deployment" deleted
```

#### `❯ kubectl get all`
```bash
NAME                 TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)    AGE
service/fileserver   ClusterIP   10.106.215.205   <none>        5005/TCP   29h
service/kubernetes   ClusterIP   10.96.0.1        <none>        443/TCP    7d23h
```

#### `❯ kubectl create deployment hello-world-deployment --image=herlesinc/hello_world`
```bash
deployment.apps/hello-world-deployment created
```

#### `❯ kubectl get pods`
```bash
NAME                                      READY   STATUS    RESTARTS   AGE
hello-world-deployment-57f58fd648-gbc5j   1/1     Running   0          111s
```

#### `❯ kubectl expose deployment hello-world-deployment --port=8088 --target-port=80`
```bash
service/hello-world-deployment exposed
```

#### `❯ kubectl get pods`
```bash
NAME                                      READY   STATUS    RESTARTS   AGE
hello-world-deployment-57f58fd648-gbc5j   1/1     Running   0          7m22s
```

#### `❯ kubectl scale deployment hello-world-deployment --replicas=4`
```bash
deployment.apps/hello-world-deployment scaled
```

#### `❯ kubectl get pods`
```bash
NAME                                      READY   STATUS              RESTARTS   AGE
hello-world-deployment-57f58fd648-gbc5j   1/1     Running             0          9m2s
hello-world-deployment-57f58fd648-hp55x   0/1     ContainerCreating   0          6s
hello-world-deployment-57f58fd648-t5ng7   0/1     ContainerCreating   0          6s
hello-world-deployment-57f58fd648-x2thr   0/1     ContainerCreating   0          6s
```

#### `❯ kubectl get pods`
```bash
NAME                                      READY   STATUS    RESTARTS   AGE
hello-world-deployment-57f58fd648-gbc5j   1/1     Running   0          9m10s
hello-world-deployment-57f58fd648-hp55x   1/1     Running   0          14s
hello-world-deployment-57f58fd648-t5ng7   1/1     Running   0          14s
hello-world-deployment-57f58fd648-x2thr   1/1     Running   0          14s
```

#### `❯ minikube ssh`
```bash
[?2004h]0;docker@minikube: ~docker@minikube:~$ [?2004l

logout
```

#### `❯ kubectl get svc`
```bash
NAME                     TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)    AGE
fileserver               ClusterIP   10.106.215.205   <none>        5005/TCP   30h
hello-world-deployment   ClusterIP   10.107.9.236     <none>        8088/TCP   2m21s
kubernetes               ClusterIP   10.96.0.1        <none>        443/TCP    7d23h
```

#### `❯ minikube ssh`
```bash
[?2004h]0;docker@minikube: ~docker@minikube:~$ curl 10.19 07.9.238 6:8088
[?2004l

        Hostname: hello-world-deployment-57f58fd648-hp55x
        IP Address: 10.244.0.41
        Hello, World![?2004h]0;docker@minikube: ~docker@minikube:~$ 
[?2004l
[?2004h]0;docker@minikube: ~docker@minikube:~$ curl 10.107.9.236:8088
[?2004l

        Hostname: hello-world-deployment-57f58fd648-x2thr
        IP Address: 10.244.0.40
        Hello, World![?2004h]0;docker@minikube: ~docker@minikube:~$ curl 10.107.9.236:8088
[?2004l

        Hostname: hello-world-deployment-57f58fd648-gbc5j
        IP Address: 10.244.0.38
        Hello, World![?2004h]0;docker@minikube: ~docker@minikube:~$ curl 10.107.9.236:8088
[?2004l

        Hostname: hello-world-deployment-57f58fd648-x2thr
        IP Address: 10.244.0.40
        Hello, World![?2004h]0;docker@minikube: ~docker@minikube:~$ curl 10.107.9.236:8088
[?2004l

        Hostname: hello-world-deployment-57f58fd648-t5ng7
        IP Address: 10.244.0.39
        Hello, World![?2004h]0;docker@minikube: ~docker@minikube:~$ curl 10.107.9.236:8088
[?2004l

        Hostname: hello-world-deployment-57f58fd648-x2thr
        IP Address: 10.244.0.40
        Hello, World![?2004h]0;docker@minikube: ~docker@minikube:~$ [?2004l

logout
```

#### `❯ kubectl get pods -o wide`
```bash
NAME                                      READY   STATUS    RESTARTS   AGE    IP            NODE       NOMINATED NODE   READINESS GATES
hello-world-deployment-57f58fd648-gbc5j   1/1     Running   0          16m    10.244.0.38   minikube   <none>           <none>
hello-world-deployment-57f58fd648-hp55x   1/1     Running   0          7m7s   10.244.0.41   minikube   <none>           <none>
hello-world-deployment-57f58fd648-t5ng7   1/1     Running   0          7m7s   10.244.0.39   minikube   <none>           <none>
hello-world-deployment-57f58fd648-x2thr   1/1     Running   0          7m7s   10.244.0.40   minikube   <none>           <none>
```

#### `❯ kubectl delete svc hello-world-deployment`
```bash
service "hello-world-deployment" deleted
```

#### `❯ kubectl get svc`
```bash
NAME         TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)    AGE
fileserver   ClusterIP   10.106.215.205   <none>        5005/TCP   30h
kubernetes   ClusterIP   10.96.0.1        <none>        443/TCP    8d
```

#### `❯ kubectl expose deployment hello-world-deployment --type=NodePort --port=3000 --target-port=80`
```bash
service/hello-world-deployment exposed
```

#### `❯ kubectl get svc`
```bash
NAME                     TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)          AGE
fileserver               ClusterIP   10.106.215.205   <none>        5005/TCP         30h
hello-world-deployment   NodePort    10.100.248.190   <none>        3000:32369/TCP   7s
kubernetes               ClusterIP   10.96.0.1        <none>        443/TCP          8d
```

#### `❯ kubectl get svc`
```bash
NAME                     TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)          AGE
fileserver               ClusterIP   10.106.215.205   <none>        5005/TCP         30h
hello-world-deployment   NodePort    10.100.248.190   <none>        3000:32369/TCP   103s
kubernetes               ClusterIP   10.96.0.1        <none>        443/TCP          8d
```

#### `❯ kubectl get all`
```bash
NAME                                          READY   STATUS    RESTARTS   AGE
pod/hello-world-deployment-57f58fd648-gbc5j   1/1     Running   0          27m
pod/hello-world-deployment-57f58fd648-hp55x   1/1     Running   0          18m
pod/hello-world-deployment-57f58fd648-t5ng7   1/1     Running   0          18m
pod/hello-world-deployment-57f58fd648-x2thr   1/1     Running   0          18m

NAME                             TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)          AGE
service/fileserver               ClusterIP   10.106.215.205   <none>        5005/TCP         30h
service/hello-world-deployment   NodePort    10.100.248.190   <none>        3000:32369/TCP   2m4s
service/kubernetes               ClusterIP   10.96.0.1        <none>        443/TCP          8d

NAME                                     READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/hello-world-deployment   4/4     4            4           27m

NAME                                                DESIRED   CURRENT   READY   AGE
replicaset.apps/hello-world-deployment-57f58fd648   4         4         4       27m
```

#### `❯ kubectl get svc`
```bash
NAME                     TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)          AGE
fileserver               ClusterIP   10.106.215.205   <none>        5005/TCP         30h
hello-world-deployment   NodePort    10.100.248.190   <none>        3000:32369/TCP   3m58s
kubernetes               ClusterIP   10.96.0.1        <none>        443/TCP          8d
```

#### `❯ kubect delete service hello-world-deployment`
```bash
```

#### `❯ kubectl delete service hello-world-deployment`
```bash
service "hello-world-deployment" deleted
```

#### `❯ kubectl expose deployment hello-world-depoyment --type=NodePort --port=80`
```bash
```

#### `❯ kubectl expose deployment hello-world-deployment --type=NodePort --port=80`
```bash
service/hello-world-deployment exposed
```

#### `❯ kubectl get svc`
```bash
NAME                     TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)        AGE
fileserver               ClusterIP   10.106.215.205   <none>        5005/TCP       30h
hello-world-deployment   NodePort    10.104.137.21    <none>        80:32185/TCP   6s
kubernetes               ClusterIP   10.96.0.1        <none>        443/TCP        8d
```

#### `❯ minikube ip`
```bash
192.168.49.2
```

#### `❯ curl 192.168.49.2:32185`
```bash
        Hostname: hello-world-deployment-57f58fd648-t5ng7
        IP Address: 10.244.0.39
        Hello, World!
```

#### `❯ curl 192.168.49.2:32185`
```bash
        Hostname: hello-world-deployment-57f58fd648-gbc5j
        IP Address: 10.244.0.38
        Hello, World!
```

#### `❯ minikube service hello-world-deployment`
```bash
|-----------|------------------------|-------------|---------------------------|
| NAMESPACE |          NAME          | TARGET PORT |            URL            |
|-----------|------------------------|-------------|---------------------------|
| default   | hello-world-deployment |          80 | http://192.168.49.2:32185 |
|-----------|------------------------|-------------|---------------------------|
🎉  Opening service default/hello-world-deployment in default browser...
Opening in existing browser session.
```

#### `❯ minikube service hello-world-deployment --url`
```bash
http://192.168.49.2:32185
```

#### `❯ kubectl delete svc hello-world-deployment`
```bash
service "hello-world-deployment" deleted
```

#### `❯ kubectl get svc`
```bash
NAME         TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)    AGE
fileserver   ClusterIP   10.106.215.205   <none>        5005/TCP   30h
kubernetes   ClusterIP   10.96.0.1        <none>        443/TCP    8d
```

#### `❯ kubectl expose deployment hello-world-deployment --type=LoadBalancer --port=80`
```bash
service/hello-world-deployment exposed
```

#### `❯ kubectl get svc`
```bash
NAME                     TYPE           CLUSTER-IP       EXTERNAL-IP   PORT(S)        AGE
fileserver               ClusterIP      10.106.215.205   <none>        5005/TCP       30h
hello-world-deployment   LoadBalancer   10.105.205.149   <pending>     80:30739/TCP   8s
kubernetes               ClusterIP      10.96.0.1        <none>        443/TCP        8d
```

#### `❯ kubectl service hello-world-deployment`
```bash
```

#### `❯ minikube service hello-world-deployment`
```bash
|-----------|------------------------|-------------|---------------------------|
| NAMESPACE |          NAME          | TARGET PORT |            URL            |
|-----------|------------------------|-------------|---------------------------|
| default   | hello-world-deployment |          80 | http://192.168.49.2:30739 |
|-----------|------------------------|-------------|---------------------------|
🎉  Opening service default/hello-world-deployment in default browser...
Opening in existing browser session.
```

#### `❯ kubectl get deploy`
```bash
NAME                     READY   UP-TO-DATE   AVAILABLE   AGE
hello-world-deployment   4/4     4            4           48m
```

#### `❯ kubectl describe deploy hello-world-deployment`
```bash
Name:                   hello-world-deployment
Namespace:              default
CreationTimestamp:      Thu, 05 Oct 2023 13:26:16 -0500
Labels:                 app=hello-world-deployment
Annotations:            deployment.kubernetes.io/revision: 1
Selector:               app=hello-world-deployment
Replicas:               4 desired | 4 updated | 4 total | 4 available | 0 unavailable
StrategyType:           RollingUpdate
MinReadySeconds:        0
RollingUpdateStrategy:  25% max unavailable, 25% max surge
Pod Template:
  Labels:  app=hello-world-deployment
  Containers:
   hello-world-wlbdv:
    Image:        herlesinc/hello_world
    Port:         <none>
    Host Port:    <none>
    Environment:  <none>
    Mounts:       <none>
  Volumes:        <none>
Conditions:
  Type           Status  Reason
  ----           ------  ------
  Progressing    True    NewReplicaSetAvailable
  Available      True    MinimumReplicasAvailable
OldReplicaSets:  <none>
NewReplicaSet:   hello-world-deployment-57f58fd648 (4/4 replicas created)
Events:
  Type    Reason             Age   From                   Message
  ----    ------             ----  ----                   -------
  Normal  ScalingReplicaSet  48m   deployment-controller  Scaled up replica set hello-world-deployment-57f58fd648 to 1
  Normal  ScalingReplicaSet  39m   deployment-controller  Scaled up replica set hello-world-deployment-57f58fd648 to 4 from 1
```

#### `❯ kubectl set image deployment hello-world-deployment hello-world-deployment=herlesinc/hello_world:2.0.0`
```bash
```

#### `❯ kubectl set image deployment hello-world-deployment hello-world-deployment=herlesinc/hello_world:2.0.0`
```bash
```

#### `❯ kubectl get all`
```bash
NAME                                          READY   STATUS    RESTARTS   AGE
pod/hello-world-deployment-57f58fd648-gbc5j   1/1     Running   0          99m
pod/hello-world-deployment-57f58fd648-hp55x   1/1     Running   0          90m
pod/hello-world-deployment-57f58fd648-t5ng7   1/1     Running   0          90m
pod/hello-world-deployment-57f58fd648-x2thr   1/1     Running   0          90m

NAME                             TYPE           CLUSTER-IP       EXTERNAL-IP   PORT(S)        AGE
service/fileserver               ClusterIP      10.106.215.205   <none>        5005/TCP       31h
service/hello-world-deployment   LoadBalancer   10.105.205.149   <pending>     80:30739/TCP   55m
service/kubernetes               ClusterIP      10.96.0.1        <none>        443/TCP        8d

NAME                                     READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/hello-world-deployment   4/4     4            4           99m

NAME                                                DESIRED   CURRENT   READY   AGE
replicaset.apps/hello-world-deployment-57f58fd648   4         4         4       99m
```

#### `❯ kubectl set image deployment hello-world-deployment hello-world-deployment=herlesinc/hello_world:2.0.0`
```bash
```

#### `❯ kubectl create deployment k8s-hello-world --image=herlesinc/hello_world:latest`
```bash
deployment.apps/k8s-hello-world created
```

#### `❯ kubectl get pods`
```bash
NAME                                      READY   STATUS    RESTARTS   AGE
hello-world-deployment-57f58fd648-gbc5j   1/1     Running   0          3h15m
hello-world-deployment-57f58fd648-hp55x   1/1     Running   0          3h6m
hello-world-deployment-57f58fd648-t5ng7   1/1     Running   0          3h6m
hello-world-deployment-57f58fd648-x2thr   1/1     Running   0          3h6m
k8s-hello-world-6887f468d7-d5kt5          1/1     Running   0          16s
```

#### `❯ kubectl get pods`
```bash
NAME                                      READY   STATUS    RESTARTS   AGE
hello-world-deployment-57f58fd648-gbc5j   1/1     Running   0          3h19m
hello-world-deployment-57f58fd648-hp55x   1/1     Running   0          3h10m
hello-world-deployment-57f58fd648-t5ng7   1/1     Running   0          3h10m
hello-world-deployment-57f58fd648-x2thr   1/1     Running   0          3h10m
k8s-hello-world-6887f468d7-d5kt5          1/1     Running   0          4m8s
```

#### `❯ kubectl get svc`
```bash
NAME                     TYPE           CLUSTER-IP       EXTERNAL-IP   PORT(S)        AGE
fileserver               ClusterIP      10.106.215.205   <none>        5005/TCP       33h
hello-world-deployment   LoadBalancer   10.105.205.149   <pending>     80:30739/TCP   156m
kubernetes               ClusterIP      10.96.0.1        <none>        443/TCP        8d
```

#### `❯ kubectl expose deployment k8s-hello-world --port=8088 --target-port=80`
```bash
service/k8s-hello-world exposed
```

#### `❯ kubectl get svc`
```bash
NAME                     TYPE           CLUSTER-IP       EXTERNAL-IP   PORT(S)        AGE
fileserver               ClusterIP      10.106.215.205   <none>        5005/TCP       33h
hello-world-deployment   LoadBalancer   10.105.205.149   <pending>     80:30739/TCP   158m
k8s-hello-world          ClusterIP      10.106.128.178   <none>        8088/TCP       9s
kubernetes               ClusterIP      10.96.0.1        <none>        443/TCP        8d
```

#### `❯ kubectl delete service k8s-hello-world`
```bash
service "k8s-hello-world" deleted
```

#### `❯ kubectl expose deployment k8s-hello-world --type=NodePort --port=80`
```bash
service/k8s-hello-world exposed
```

#### `❯ kubectl get svc`
```bash
NAME                     TYPE           CLUSTER-IP       EXTERNAL-IP   PORT(S)        AGE
fileserver               ClusterIP      10.106.215.205   <none>        5005/TCP       33h
hello-world-deployment   LoadBalancer   10.105.205.149   <pending>     80:30739/TCP   160m
k8s-hello-world          NodePort       10.108.132.44    <none>        80:30083/TCP   7s
kubernetes               ClusterIP      10.96.0.1        <none>        443/TCP        8d
```

#### `❯ kinikube service k8s-hello-world`
```bash
```

#### `❯ minikube service k8s-hello-world`
```bash
|-----------|-----------------|-------------|---------------------------|
| NAMESPACE |      NAME       | TARGET PORT |            URL            |
|-----------|-----------------|-------------|---------------------------|
| default   | k8s-hello-world |          80 | http://192.168.49.2:30083 |
|-----------|-----------------|-------------|---------------------------|
🎉  Opening service default/k8s-hello-world in default browser...
Opening in existing browser session.
```

#### `❯ kubectl get pods`
```bash
NAME                                      READY   STATUS    RESTARTS   AGE
hello-world-deployment-57f58fd648-gbc5j   1/1     Running   0          3h25m
hello-world-deployment-57f58fd648-hp55x   1/1     Running   0          3h16m
hello-world-deployment-57f58fd648-t5ng7   1/1     Running   0          3h16m
hello-world-deployment-57f58fd648-x2thr   1/1     Running   0          3h16m
k8s-hello-world-6887f468d7-d5kt5          1/1     Running   0          9m46s
```

#### `❯ kubectl scale deployment k8s-hello-world --replicas=4`
```bash
deployment.apps/k8s-hello-world scaled
```

#### `❯ minikube service k8s-hello-world`
```bash
|-----------|-----------------|-------------|---------------------------|
| NAMESPACE |      NAME       | TARGET PORT |            URL            |
|-----------|-----------------|-------------|---------------------------|
| default   | k8s-hello-world |          80 | http://192.168.49.2:30083 |
|-----------|-----------------|-------------|---------------------------|
🎉  Opening service default/k8s-hello-world in default browser...
Opening in existing browser session.
```

#### `❯ kubectl set image deployment k8s-hello-world k8s-hello-world=herlesinc/hello_world:2.0.0`
```bash
```

#### `❯ kubectl create deployment k8s-web-hello --image=herlesinc/herles_world:latest`
```bash
deployment.apps/k8s-web-hello created
```

#### `❯ kubectl get pods`
```bash
NAME                                      READY   STATUS         RESTARTS   AGE
hello-world-deployment-57f58fd648-gbc5j   1/1     Running        0          3h40m
hello-world-deployment-57f58fd648-hp55x   1/1     Running        0          3h31m
hello-world-deployment-57f58fd648-t5ng7   1/1     Running        0          3h31m
hello-world-deployment-57f58fd648-x2thr   1/1     Running        0          3h31m
k8s-hello-world-6887f468d7-d5kt5          1/1     Running        0          25m
k8s-hello-world-6887f468d7-k6dtk          1/1     Running        0          14m
k8s-hello-world-6887f468d7-kgfqm          1/1     Running        0          14m
k8s-hello-world-6887f468d7-wjphw          1/1     Running        0          14m
k8s-web-hello-6457dc4f8-w9lvr             0/1     ErrImagePull   0          8s
```

#### `❯ kubectl delete deployment k8s-web-hello`
```bash
deployment.apps "k8s-web-hello" deleted
```

#### `❯ kubectl create deployment k8s-web-hello --image=herlesinc/hello_world:latest`
```bash
deployment.apps/k8s-web-hello created
```

#### `❯ kubectl get pods`
```bash
NAME                                      READY   STATUS    RESTARTS   AGE
hello-world-deployment-57f58fd648-gbc5j   1/1     Running   0          3h42m
hello-world-deployment-57f58fd648-hp55x   1/1     Running   0          3h33m
hello-world-deployment-57f58fd648-t5ng7   1/1     Running   0          3h33m
hello-world-deployment-57f58fd648-x2thr   1/1     Running   0          3h33m
k8s-hello-world-6887f468d7-d5kt5          1/1     Running   0          26m
k8s-hello-world-6887f468d7-k6dtk          1/1     Running   0          16m
k8s-hello-world-6887f468d7-kgfqm          1/1     Running   0          16m
k8s-hello-world-6887f468d7-wjphw          1/1     Running   0          16m
k8s-web-hello-5b85fc8796-cjlp9            1/1     Running   0          8s
```

#### `❯ kubectl expose deployment k8s-web-hello --type=NodePort --port=80`
```bash
service/k8s-web-hello exposed
```

#### `❯ kubectl get all`
```bash
NAME                                          READY   STATUS    RESTARTS   AGE
pod/hello-world-deployment-57f58fd648-gbc5j   1/1     Running   0          3h43m
pod/hello-world-deployment-57f58fd648-hp55x   1/1     Running   0          3h34m
pod/hello-world-deployment-57f58fd648-t5ng7   1/1     Running   0          3h34m
pod/hello-world-deployment-57f58fd648-x2thr   1/1     Running   0          3h34m
pod/k8s-hello-world-6887f468d7-d5kt5          1/1     Running   0          27m
pod/k8s-hello-world-6887f468d7-k6dtk          1/1     Running   0          17m
pod/k8s-hello-world-6887f468d7-kgfqm          1/1     Running   0          17m
pod/k8s-hello-world-6887f468d7-wjphw          1/1     Running   0          17m
pod/k8s-web-hello-5b85fc8796-cjlp9            1/1     Running   0          77s

NAME                             TYPE           CLUSTER-IP       EXTERNAL-IP   PORT(S)        AGE
service/fileserver               ClusterIP      10.106.215.205   <none>        5005/TCP       33h
service/hello-world-deployment   LoadBalancer   10.105.205.149   <pending>     80:30739/TCP   179m
service/k8s-hello-world          NodePort       10.108.132.44    <none>        80:30083/TCP   19m
service/k8s-web-hello            NodePort       10.100.21.252    <none>        80:30400/TCP   10s
service/kubernetes               ClusterIP      10.96.0.1        <none>        443/TCP        8d

NAME                                     READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/hello-world-deployment   4/4     4            4           3h43m
deployment.apps/k8s-hello-world          4/4     4            4           27m
deployment.apps/k8s-web-hello            1/1     1            1           78s

NAME                                                DESIRED   CURRENT   READY   AGE
replicaset.apps/hello-world-deployment-57f58fd648   4         4         4       3h43m
replicaset.apps/k8s-hello-world-6887f468d7          4         4         4       27m
replicaset.apps/k8s-web-hello-5b85fc8796            1         1         1       77s
```

##### `❯ kubectl scale deployment k8s-web-hello --replicas=4`
```bash
deployment.apps/k8s-web-hello scaled
```

##### `❯ kubectl set image deployment k8s-web-hello k8s-web-hello=herlesinc/hello_world:2.0.0`
```bash
```

#### `❯ kubectl scale deployment hello-world-deployment --replicas=0`
```bash
deployment.apps/hello-world-deployment scaled
```

#### `❯ kubectl scale deployment k8s-hello-world --replicas=0`
```bash
deployment.apps/k8s-hello-world scaled
```

#### `❯ kubectl scale deployment k8s-web-hello --replicas=1`
```bash
deployment.apps/k8s-web-hello scaled
```

#### `❯ kubectl get service`
```bash
NAME                     TYPE           CLUSTER-IP       EXTERNAL-IP   PORT(S)        AGE
fileserver               ClusterIP      10.106.215.205   <none>        5005/TCP       34h
hello-world-deployment   LoadBalancer   10.105.205.149   <pending>     80:30739/TCP   3h17m
k8s-hello-world          NodePort       10.108.132.44    <none>        80:30083/TCP   37m
k8s-web-hello            NodePort       10.100.21.252    <none>        80:30400/TCP   18m
kubernetes               ClusterIP      10.96.0.1        <none>        443/TCP        8d
```

#### `❯ minikube service k8s-web-hello`
```bash
|-----------|---------------|-------------|---------------------------|
| NAMESPACE |     NAME      | TARGET PORT |            URL            |
|-----------|---------------|-------------|---------------------------|
| default   | k8s-web-hello |          80 | http://192.168.49.2:30400 |
|-----------|---------------|-------------|---------------------------|
🎉  Opening service default/k8s-web-hello in default browser...
Opening in existing browser session.
```

#### `❯ kubectl delete service k8s-hello-world`
```bash
service "k8s-hello-world" deleted
```

#### `❯ kubectl get svc`
```bash
NAME                     TYPE           CLUSTER-IP       EXTERNAL-IP   PORT(S)        AGE
fileserver               ClusterIP      10.106.215.205   <none>        5005/TCP       34h
hello-world-deployment   LoadBalancer   10.105.205.149   <pending>     80:30739/TCP   3h18m
k8s-web-hello            NodePort       10.100.21.252    <none>        80:30400/TCP   19m
kubernetes               ClusterIP      10.96.0.1        <none>        443/TCP        8d
```

#### `❯ kubectl delete service hello-world-deployment`
```bash
service "hello-world-deployment" deleted
```

#### `❯ kubectl get svc`
```bash
NAME            TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)        AGE
fileserver      ClusterIP   10.106.215.205   <none>        5005/TCP       34h
k8s-web-hello   NodePort    10.100.21.252    <none>        80:30400/TCP   19m
kubernetes      ClusterIP   10.96.0.1        <none>        443/TCP        8d
```

#### `❯ kubectl rollout status deploy k8s-web-hello`
```bash
deployment "k8s-web-hello" successfully rolled out
```

#### `❯ minikube dashboard`
```bash
    ▪ Using image docker.io/kubernetesui/dashboard:v2.7.0
    ▪ Using image docker.io/kubernetesui/metrics-scraper:v1.0.8
💡  Some dashboard features require the metrics-server addon. To enable all features please run:

	minikube addons enable metrics-server	


🎉  Opening http://127.0.0.1:44377/api/v1/namespaces/kubernetes-dashboard/services/http:kubernetes-dashboard:/proxy/ in your default browser...
Opening in existing browser session.
