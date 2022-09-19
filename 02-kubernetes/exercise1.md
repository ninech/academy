# Important links

If you get stuck anywhere, try to find help here or ask the teacher:
https://support.nine.ch/categories/managed-gke

# kubectl exercises

In this exercise you will get familiar with kubectl since it is really important to master.
Before we begin, take a quick look at the kubectl cheat sheet:
https://kubernetes.io/docs/reference/kubectl/cheatsheet/

# 1

We covered what a Kubernetes namespace is in the theory part of the course.
If you want a reminder you can read about namespaces here: https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces/

Kubernetes comes with a couple of default namespaces.
Try to list them with kubectl. Hint: use the kubectl get command. You can always add a -h flag to get some help.

# 2

Try to list the namespaces with the following command:
```
$ kubens
```

You will see that you are in the default namespace.
If you try to list anything in this namespace, you will notice that you don't have the permissions.
```
$ kubectl get all
```

Let's create our own namespace.
This is a shared cluster, so please use the following convention: academy- firstname i.e. academy-max
We need to use the kubectl create command for this.
Hint: Use the -h flag for an example.

After you created the namespace try to see the details using the kubectl describe command.
Finally, use kubens and set it to your namespace you just created:
```
$ kubens <your namespace>
```

# 3

Let's say that this namespace you just created is a development environment of our fictional app called "cool-app".

It would maybe make sense to label that namespace.
For this we need to edit the namespace using the kubectl edit command.

Add the following labels:
```
env: dev
app: cool-app
```

Your namespace should already have one label. Put these two under it.
If you need help you can find some examples here:
https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/#syntax-and-character-set

# 4

If you do a kubectl get all, you obviously won't see anything, so let's create a pod!

We will need the kubectl run command for this. Again, like with every command check out kubectl run -h flag!

```
kubectl run -h
```

Use the following parameters:
--image=nginx
--port=80
--restart=Never

List the detail of the pod with the get command. Maybe try out the flag -o wide!
Also describe the pod using the kubectl describe command!

# 5

Now let's see if we can see the logs of the container running in our newly created pod.

Use the kubectl logs command!

Optional:
If you wanna maybe see the k8s dashboard in action, you can open runway again and in the Services tab, you can follow the link of to the k8s dashboard.
Set your namespace there and check out the pod.

# 6

Now let's delete the pod. Use the delete command!
Do a get command afterwards. What happens?

# 7

We have created now a pod directly, but usually we don't want to create it directly.
Let's create a deployment! Use the k8s.gcr.io/echoserver:1.4 image.

When you create a Deployment, 3 resources are deployed. Deployments, ReplicaSet and Pods. Check them all out. Make sure to understand what happens!

# 8

When your app becomes more popular, you will need to scale. Luckily that is quite easy with k8s.
When you described the deployment and the replicaset, you might have seen the replica field.
Scale the deployment to 3 or more replicas and check out what happens to three resources you described above.
Use the scale kubectl command!

# 9

K8s is supposed to be self-healing, right? Let's prove it. Delete any of the pods of the deployment.
What happens? Checkout the events as well the events with kubectl get events.

# 10

Delete the deployment

# 11

Until now, you have created and deleted resources using the kubectl commands.
Now we are going to use the actual resource definitions, how you would do it in the real world.

Check out this [file](templates/1/11.yaml) `templates/1/11.yaml`

You will see a deployment resource definition. Describe each line and write it down on the right behind the comment.

# 12

Create a deployment out of the file above. Use the kubectl apply command.

# 13 

Change the replica count in the file and apply it again. What happens?

# 14

Delete the deployment.

# Solutions

You can find the solutions [here](solutions/1.md) `solutions/1.md`.


[Back to Overview](https://github.com/ninech/academy)