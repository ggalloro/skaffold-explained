# Skaffold Explained

. 


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
skaffold dev --port-forward
```



```
portForward:
  - resourceType: deployment
    resourceName: scdongcp-app
    port: http
    localPort: 4503
```



```
skaffold build --file-output artifacts.json 
```



```
docker images
```

```
test:
- image: scdongcp-app
  custom:
    - command: echo This is a custom test command
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

