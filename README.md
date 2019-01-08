in your yaml:

```
apiVersion: v1
kind: Pod
metadata:
  name: curl-with-ambassador
spec:
  containers:
  - name: main
    image: tutum/curl
    command: ["sleep", "9999999"]
  - name: ambassador                         
    image: dyhpoon/kubectl-proxy
```

run a shell inside the `main` container, and we can `curl` kubernetes's API through the ambassador container
```
curl localhost:8001
```
