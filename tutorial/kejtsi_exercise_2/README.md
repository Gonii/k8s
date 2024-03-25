 ### Exercise 2: Deployments and Rolling Updates **Task**: Create a Deployment named `webapp` using the `nginx:1.17` image with 3 replicas. Expose the deployment internally using a ClusterIP service on port 80. Then, perform a rolling update to `nginx:1.18`. Ensure zero downtime and document the steps.


 $ kubectl apply -f deployment.yaml # creates deployment and service
 $ kubectl apply -f deployment_update.yaml # updates nginx image to 1.18
 