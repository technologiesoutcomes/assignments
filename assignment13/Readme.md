### Assignment 13

1) Using the Terraform in this repository (https://github.com/technologiesoutcomes/simple-eks), deploy the EKS cluster in your AWS account.
   Deploy the games-2048 application and access it through the load balancer address on your browser.
   
2) Go to the samples-apps directory and run the following;

* Deploy the manifest in nginx.yml to the cluster
* Deploy the manifest in the nginx-deployment.yml
* Run the commands to view the deployments and pods running on your cluster.

3) Using an imperative style, delete the pods and one of the pods of the deployment and observer what happens.

4) Create a new nginx pod using the following:
```
kubectl run new-nginx --image=nginx --port=80
```
Get the pod's IP address using one of the following:
```
kubectl get pod nginx -o wide

kubectl get pod nginx -o yaml
```

Now you want to attempt a pod-to-pod communication by running the following. Substitute the placeholder ?????? with the pod IP from above.

```
 kubectl run busybox --image=busybox --rm -it --restart=Never \
 -- wget ???????:80
```

Is pod-to-pod communication possible within a cluster?

Why might it not be a good idea to configure a pod to communicate with another pod thought the server pod IP address?

5) Run the following commands to create a deployment and a service pointing to the deployment.
```
kubectl create deployment echoserverd --image=k8s.gcr.io/echoserver:1.10 \
 --replicas=5

kubectl expose deployment echoserverd --port=80 --target-port=8080
```

Run the following to view the deployment and service you created above.

```
kubectl describe deployment echoserverd

kubectl describe service echoserverd
```

What are the pod IP addresses associated with the service?

Run the following commands to retrieve the endpoints IP addresses
```
kubectl get endpoints echoserverd
```

What type of service was created?

 

### Ensure that you destroy the cluster when you are done.
