# Important links

If you get stuck anywhere, try to find help here or ask the teacher:
https://support.nine.ch/categories/managed-gke

# 1

Lets take a look at services. First of we need to create a deployment. Take a look at this [file](templates/2/1.yaml) `templates/2/1.yaml`.
Make sure you understand every line in it! If you have trouble ask the teacher.

Create the deployment out of the file in your namespace on the nine managed GKE cluster.
Check out what the the deployment created.

Now lets expose our deployment to the outside world.

Use the kubectl expose command. Create a LoadBalancer service!

Check the service out and try to open the application in the browser or use curl.

# 2

Delete the deployment and the service from above.

# 3 

Until now, we worked with simple applications. Now, it is time for a big exercise.
Check out this [file](templates/2/3.yaml) `templates/2/3.yaml`.

Here you will find TODO comments instructing you what to do.
You can see the rough architecture here:
https://raw.githubusercontent.com/dockersamples/example-voting-app/master/architecture.png

Use your own created namespace for this exercise still.
The db pod should use a persistent storage.
The redis pod should not have persistent storage.
Voting and result app should be reachable from the outside.

There are solutions (here)[], but we really recommend to try to do it on your own(google first!).

Apply the file and check out what was created.

If everything is working properly, you should be able to vote and check the result in your browser.

# 4

Clean up by deleting everything you just created :D.

# 5

The last thing we have to look at are ConfigMaps.

Check out the [file](templates/2/5.txt) `templates/2/5.txt`.
We want to use that file as the data of our ConfigMap.

Use the create command to create it. Hint: Use --from-file and give the txt file as a parameter.

# 6

Delete the ConfigMap above and create another one. This time use ---from-literal!
Use the key city and as a value a city of your choice.

Create a Pod from this file and check its logs to see if your city is in the env variables.

# 7

Delete the pod and configmap.

# 5

You can find the solutions [here](solutions/2.md) `solutions/2.md`.
