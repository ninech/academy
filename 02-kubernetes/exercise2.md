# Important links

If you get stuck anywhere, try to find help here or ask the teacher:
https://support.nine.ch/categories/managed-gke

# 1

Lets take a look at services. First of we need to create a deployment. Take a look at this [file](templates/2/1.yaml) `templates/2/1.yaml`.
Make sure you understand every line in it! If you have trouble ask the teacher.

Create the deployment out of the file in your namespace on the nine managed GKE cluster.
Check out what the the deployment created.

Now lets expose our deployment to the outside world.

Use the kubectl expose command. Create a LoadBalancer service! Not a ClusterIP service!!

Check the service out and try to open the application in the browser or use curl.

# 2

Delete the deployment and the service from above.

# 3

Until now, we worked with simple applications. Now, it is time for a big exercise.
Check out this [file](templates/2/3.yaml) `templates/2/3.yaml`.

This is a dockersamples demo app from the dockercon 2018.
The application has 3 microservices called db, words and web.
It generates setences using the words in the db.

We assume that the app and the containers are configured properly.

Your job is to finish all the instructions that are in the TODO comments.
Use your own created namespace for this exercise still.

If everything is working properly, words should appear in your browser.
You should also see the IP where the word is coming from.
Which IP is that?


# 4

Now lets delete everything again you created and change the Service db and web a bit.
Add clusterIP: None under the type and apply it again. What difference do you see in the browser? What are those IPs?

Delete everything again when you are done.

Hint: You can use the delete command with the -f flag!
```
$ kubectl delete -f 3.yaml
```

# 5

The last thing we have to look at are ConfigMaps.

Check out the [file](templates/2/5.txt) `templates/2/5.txt`.
We want to use that file as the data of our ConfigMap.

Use the create command to create it. Hint: Use --from-file and give the txt file as a parameter.

# 6

Delete the ConfigMap above and create another one. This time use ---from-literal!
Use the key city and as a value a city of your choice.

Create a Pod from this [file](templates/2/6.yaml) `templates/2/6.yaml` and check its logs to see if your city is in the env variables.

# 7

Delete the pod and configmap.

# 8

You can find the solutions [here](solutions/2.md) `solutions/2.md`.


# 9

If you finish ahead of time, you can do this optional exercise.
This is a similiar exercise to # 3.
If you have your own containers ready, you can also try to get your own app to run on the cluster instead of this exercise.

Check out this [file](templates/2/9.yaml) `templates/2/9.yaml`.

Here you will find TODO comments instructing you what to do.
You can see the rough architecture here:
https://raw.githubusercontent.com/dockersamples/example-voting-app/master/architecture.png
Use your own created namespace for this exercise still.
Voting and result app should be reachable from the outside.

Apply the file and check out what was created.

Sadly the containers itself are having trouble saving the data in the DB. So if everything looks good in the cluster and you can reach the 2 pages, you can assume you did it correctly. If you vote, this app will probably not react :/

You can find the solutions [here](solutions/9.yaml) `solutions/9.yaml`.

# 10 

Clean up by deleting everything you just created.


[Back to Overview](https://github.com/ninech/academy)
