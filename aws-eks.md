## Elastic Kubernetes Service (EKS)
Create a cluster
```shell
aws eks create-cluster --name (cluster name)
```

Delete a cluster
```shell
aws eks delete-cluster --name (cluster name)
```

List descriptive information about a cluster
```shell
aws eks describe-cluster --name (cluster name)
```

List clusters in your default region
```shell
aws eks list-clusters
```
