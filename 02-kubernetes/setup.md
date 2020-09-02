# Install kubectl

To interact with a kubernetes cluster in a good and not clicky way, you should always use kubectl.

We will install it with gcloud since you should still have it installed on your machine from the docker exercise.
If not, check out the installation guide here:
https://cloud.google.com/sdk/docs/downloads-interactive

Check if gcloud is working properly:
```
$ gcloud version
```

Install kubectl with the following command:
```
$ gcloud components install kubectl
```

# kubectl autocomplete and alias

We recommend autocomplete since it makes your live that much easier!

Bash:
```
$ source <(kubectl completion bash) # setup autocomplete in bash into the current shell, bash-completion package should be installed first.
$ echo "source <(kubectl completion bash)" >> ~/.bashrc # add autocomplete permanently to your bash shell.

```


ZSH:
```
$ source <(kubectl completion zsh)  # setup autocomplete in zsh into the current shell
$ echo "[[ $commands[kubectl] ]] && source <(kubectl completion zsh)" >> ~/.zshrc # add autocomplete permanently to your zsh shell

```

If you dont want to type out kubectl out everytime, you can set up a alias like k or kc:
```
$ alias k=kubectl
$ complete -F __start_kubectl k
```

# Connecting to the nine managed GKE cluster

Head over to runway, nine's UI of the nine managed GKE cluster, and log yourself in.
https://runway.ninegcp.ch/

There are different tabs. Go check them out! You can see what nine managed GKE offers.

After you ready to move on, go over to https://console.cloud.google.com/ and log yourself in with the ninegcp account.
There you can see the Google Cloud Platform and what it offers. We recommend you check it out a bit!

On runway you will see a section called "Logging into the cluster" under the Google Kubernetes Engine tab.
Follow the steps there.

# Install kubectx and kubens

Finally the last piece that is missing:
https://github.com/ahmetb/kubectx

Install it and try it with the following command:
```
$ kubectx
gke_nine-academy-854265_europe-west6_academy
```

# Continue to the exercises
 
 You are ready to get started. [Here](exercise1.md)