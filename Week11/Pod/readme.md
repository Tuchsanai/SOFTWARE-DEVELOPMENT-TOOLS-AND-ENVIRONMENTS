
### 1 Create a new file called nginx-pod.yaml with the following content:

```
nano nginx-pod.yaml
```

### 2 Add the following content

```
apiVersion: v1
kind: Pod
metadata:
  name: nginx-lab
  labels:
    app: nginx
spec:
  containers:
  - name: nginx
    image: nginx:latest
    ports:
    - containerPort: 80

```



## 3.Save and close the file.
```
Ctrl+X, then Y, then Enter.
```