Scenario: You have been alerted to a problem in the default namespace where a Deployment named complex-app is behaving unexpectedly. The Pods are repeatedly entering a CrashLoopBackOff state shortly after starting. The Deployment is supposed to run a custom application built on the node:14-alpine image.


apiVersion: apps/v1
kind: Deployment
metadata:
  name: complex-app
  namespace: default
spec:
  replicas: 3
  selector:
    matchLabels:
      app: complex-app
  template:
    metadata:
      labels:
        app: complex-app
    spec:
      containers:
      - name: main-container
        image: node:14-alpine
        command: ["node"]
        args: ["app.js"]
        resources:
          limits:
            cpu: "100m"
            memory: "100Mi"
        livenessProbe:
          httpGet:
            path: /health
            port: 3000
          initialDelaySeconds: 15
          periodSeconds: 5
      - name: sidecar-container
        image: busybox
        args: ["sleep", "1000"]
