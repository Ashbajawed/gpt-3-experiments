# Kubernetes

Kubernetes YAML manifest building tasks, as proposed by [/u/GhostManaged on Reddit](https://www.reddit.com/r/MachineLearning/comments/hc4i4l/d_i_will_be_running_experiments_on_openais_gpt3/fvcx2p6/).

## Prompt

```
Input: expose wordpress on port 80
Output:
apiVersion: v1
kind: Service
metadata:
  name: wordpress-service
spec:
  selector:
    app: wordpress
  ports:
    - protocol: TCP
      port: 80

Input: deploy wordpress with 2 replicas
Output:
apiVersion: apps/v1
kind: Deployment
metadata:
  name: wordpress-deployment
  labels:
    app: wordpress
spec:
  replicas: 3
  selector:
    matchLabels:
      app: wordpress
  template:
    metadata:
      labels:
        app: wordpress
    spec:
      containers:
      - name: wordpress
        image: wordpress:3.5.0
        ports:
        - containerPort: 80

Input: deploy Elasticsearch
Output:
```
