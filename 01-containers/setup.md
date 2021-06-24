# Install docker

Follow the guides and install docker for your distro/OS.

[Ubuntu](https://docs.docker.com/engine/install/ubuntu/)

[Fedora](https://docs.docker.com/engine/install/fedora/)

[Arch](https://wiki.archlinux.org/index.php/docker)

[Mac](https://docs.docker.com/docker-for-mac/install/)

[Windows](https://docs.docker.com/docker-for-windows/install/)

## Test your installation

Open a terminal and run the following docker command. You should get a similar output.

```
$ sudo docker --version
Docker version 19.03.5, build 633a0ea
```

Try to run the hello-world image:

```
$ sudo docker run hello-world

Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
ca4f61b1923c: Pull complete
Digest: sha256:ca0eeb6fb05351dfc8759c20733c91def84cb8007aa89a5bf606bc8b315b9fc7
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.
...
```

Try to list the image:

```
sudo docker image ls
```

Try to list the container itself:

```
$ sudo docker ps --all

CONTAINER ID     IMAGE           COMMAND      CREATED            STATUS
54f4984ed6a8     hello-world     "/hello"     20 seconds ago     Exited (0) 19 seconds ago
```

## Sudo

As you noticed, the docer commands require you to be root.
To not type sudo always, considering doing the following on Linux:

```
$ sudo groupadd docker
$ sudo usermod -aG docker $USER
```

You will need to relog your user or do the follwing:
```
$ newgrp docker
```

Be careful, as this gives the specified user root equivalent privileges!

Verify:

```
$ docker run hello-world
```


[If you finished all the above, continue with exercise >](exercise.md)