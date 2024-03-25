### Exercise 3: Networking
**Task**: Configure Network Policies to achieve the following:
- Allow traffic from the `frontend` namespace to a service in the `backend` namespace on TCP port 6379 only.
- Deny all other inbound traffic to the `backend` namespace.
- Ensure that pods in the `backend` namespace can communicate with each other.