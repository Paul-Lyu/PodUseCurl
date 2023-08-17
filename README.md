# PodUseCurl
Create a Pod let `curl` command be used in a Pod to retrieve all Pods in the `default` namespace
Use the following command to create the Pod in Kubernetes cluster:
```sh
kubectl apply -f curl-pod.yaml
```
After the Pod is created, use the following command to execute pod:
```sh
kubectl exec -it curl-pod -- /bin/sh
```
Use the curl command to retrieve all pod in `default` namespace:
```sh
curl -k -H "Authorization: Bearer $(cat /var/run/secrets/kubernetes.io/serviceaccount/token)" \
     https://kubernetes.default.svc.cluster.local/api/v1/namespaces/default/pods
```
