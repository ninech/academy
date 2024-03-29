# helm exercises

In this exercise you will get familiar with helm and how it makes your life easier.

# Install helm

Go to the following link and install helm:
https://helm.sh/docs/intro/install/

To see if everything is set up properly run the following command:

```
$ helm version

version.BuildInfo{Version:"v3.2.1", GitCommit:"fe51cd1e31e6a202cba7dead9552a6d418ded79a", GitTreeState:"clean", GoVersion:"go1.13.10"}
```

# 1

Let's add a repository! Use the repo located at https://grafana.github.io/helm-charts

Use the helm command add repo.
Call this repo grafana.
After you added it, use the search command and see what is available.

# 2

Now let's install a helm chart into our cluster.
Install the grafana chart from the grafana repo.
Make sure to search the repo first.

Check out what happens!

# 3

Try to see all releases with the list command.

# 4

Uninstall the helm chart

# 5

Now it's time to create our own helm chart. Use the helm create command for
this.

We can now edit the values yaml to customize our chart. Do the following:
- set the replicas to 3 and enable autoscaling.
- enable the ingress and remove the host, also set the path to be /<yourname>

Create a helm release out of your chart.

Controlling:
- Can you curl the ingress properly?
- How many replicas are deployed? Why is that amount deployed? Discuss your
  reasoning in the class.

# Solutions

Check the [solutions](solutions/3.md) `solutions/3.md`
