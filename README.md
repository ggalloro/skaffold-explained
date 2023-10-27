# Skaffold Explained

## Code, assets and commands used in the ["Skaffold Explained" talk](https://youtu.be/9on9kJJs_LQ) at Cloud Native Rejekts EU 2023. 


```
git clone https://github.com/ggalloro/skaffold-explained/ \
&& cd skaffold-explained/go
```


```
skaffold init
```

```
minikube start
```



```
eval $(minikube -p minikube docker-env)
skaffold config set --kube-context minikube local-cluster true
```

```
portForward:
  - resourceType: deployment
    resourceName: skaffold-expl-app
    port: http
    localPort: 4503
```
```
test:
- image: skaffold-expl-app
  custom:
    - command: echo This is a custom test command
```

```
skaffold dev
```



```
skaffold build --file-output artifacts.json 
```



```
docker images
```




```
skaffold test --build-artifacts artifacts.json
```


```
skaffold deploy -a artifacts.json
```


```
kubectl get pods,deploy,svc
```


```
skaffold delete
```


```
skaffold render -a artifacts.json --output render.yaml
```

```
skaffold apply render.yaml
```



```
kubectl get pods,deploy,svc
```


```
skaffold delete
rm artifacts.json
```


```
skaffold run --tail
```


```
cd ../go-multi
```
```
minikube stop
eval $(minikube -p minikube docker-env -u)
```

```
skaffold build --file-output artifacts.json --default-repo europe-docker.pkg.dev/galloro-host/demos
```

```
skaffold deploy -a artifacts.json -p qa --kube-context=qa-cluster
```

```
kubectl --context=qa-cluster get pods,svc
```

```
skaffold deploy -a artifacts.json -p prod --kube-context=prod-cluster
```

```
kubectl --context=prod-cluster get pods,svc
```

