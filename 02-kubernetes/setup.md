# Install kubectl

[Click here.](https://kubernetes.io/docs/tasks/tools/)

# [Linux & Mac]kubectl autocomplete and alias

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

# Install kubelogin

[Click here.](https://github.com/int128/kubelogin#setup)

You only need to install it. The kubeconfig already is configured properly.

# Connecting to cluster

Copy the content of the kubeconfig to `~/.kube/config` or export it `export
KUBECONFIG=<path-to-file>kubeconfig`

# Test connection

Test your connection by using this command:
```
$ kubectl get namespace
cattle-fleet-system           Active   4h22m
cattle-impersonation-system   Active   4h23m
cattle-system                 Active   4h25m
default                       Active   4h25m
kube-node-lease               Active   4h25m
kube-public                   Active   4h25m
kube-system                   Active   4h25m
local                         Active   4h23m
nine-system                   Active   4h22m
```

# Install kubectx and kubens

Finally the last piece that is missing:
https://github.com/ahmetb/kubectx

Install it and try it with the following command:
```
$ kubectx
nine-academy
```

# Continue to the exercises
 
 You are ready to get started. [Here](exercise1.md)