# 1

You should still have the nginx deployment running in your namespace from the
last exercise.

Let's try to access the nginx web server by using the `kubectl port-forward`
command. Try to forward the container port 80 to your local machine's port 8080.

Once you executed your command, open the proper URL in your browser? What is the URL?

Check page 54 in the slides if you need any help or ask.

Delete the deployment afterwards.

# 2

Let's take a look at services. First of we need to create a deployment. Take a look at this [file](templates/2/2.yaml) `templates/2/2.yaml`.
Make sure you understand every line in it! If you have trouble ask the teacher.

Create the deployment out of the file in your namespace.
Check out what the deployment created.

Now let's expose our deployment to the outside world.

Use the kubectl expose command. Create a LoadBalancer service! Not a ClusterIP service!!

Check the service out and try to open the application in the browser or use curl.

# 3

Delete the deployment and the service from above.

# 4

Take a look at this [file](templates/2/4.yaml) `templates/2/4.yaml`.

Try to create a service that targets the pod above.
Once you created both resources, try to port-forward the service to your local
machine on port 8080.


# 5

Now we are going to take a look at the ingress.
Take a look at this [file](templates/2/5.yaml) `templates/2/5.yaml`.

Deploy the two services and the two pods and the ingress.
However, first you need to fix the ingress resource.

Make sure to add the path properly.

Ask your teacher for the URL of the ingress controller.
How can you access your apps? What is the advantage of the ingress instead of
LoadBalancer?

Delete the ingress and the other resources.

# 6

Until now, we worked with simple applications. Now, it is time for a big exercise.
Check out this [directory](templates/2/6/) `templates/2/6/`.

This is a dockersamples demo app from the dockercon .
The application has 3 microservices called db, api and web.
It generates sentences using the words in the db.

We assume that the app and the containers are configured properly.

Your job is to finish all the instructions that are in the comments.
Use your own created namespace for this exercise still.

Start with the api.yaml and go to the db.yaml and then to the web.yaml.
The exercises get progressively harder.

If everything is working properly, words should appear in your browser.
You should also see the IP where the word is coming from.
Which IP is that?

# 7

The last thing we have to look at are ConfigMaps.

Check out the [file](templates/2/7.txt) `templates/2/7.txt`.
We want to use that file as the data of our ConfigMap.

Use the create command to create it. Hint: Use --from-file and give the txt file as a parameter.

# 8

Delete the ConfigMap above and create another one with the same name `cm`. This time use ---from-literal!
Use the key city and as a value a city of your choice.

Create a Pod from this [file](templates/2/8.yaml) `templates/2/8.yaml` and check its logs to see if your city is in the env variables.

# 9

Delete the pod and configmap.

# 10

You can find the solutions [here](solutions/2.md) `solutions/2.md`.


# 11

If you finish ahead of time, you can do this optional exercise.
This is a similliar exercise to # 6.
If you have your own containers ready, you can also try to get your own app to run on the cluster instead of this exercise.

Check out this [file](templates/2/11.yaml) `templates/2/11.yaml`.

Here you will find TODO comments instructing you what to do.
You can see the rough architecture here:
![Architecture](https://raw.githubusercontent.com/dockersamples/example-voting-app/master/architecture.png)
Use your own created namespace for this exercise still.
Voting and result app should be reachable from the outside.

Apply the file and check out what was created.

Sadly the containers itself are having trouble saving the data in the DB. So if everything looks good in the cluster and you can reach the 2 pages, you can assume you did it correctly. If you vote, this app will probably not react :/

You can find the solutions [here](solutions/11.yaml) `solutions/11.yaml`.

# 12

Clean up by deleting everything you just created.


[Back to Overview](https://github.com/ninech/academy)
