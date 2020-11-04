# Dockerfile

In this exercise you will refresh your Dockerfile skills.

## 1. Analyze a Dockerfile

Open the exercise 1 [folder](templates/1) `templates/1`.
Open the Dockerfile that is located in it.

Describe each build instruction within that Dockerfile with a comment (a line starting with `#`) above the instruction.
Focus on the Docker commands instead of the others. For example, describe what the RUN command does instead of npm install.

## 2. Multi-stage builds

In this exercise, you will learn the difference and benefits of using multi-stage builds.

Open the exercise 2 [folder](templates/2) `templates/2`.

You may find a `hello.go` and a `Dockerfile`.
If you have the [Go toolchain](https://golang.org/doc/install) installed, you can run the go file to see what it does by executing `go run hello.go` or maybe you might understand it by just looking at the code.

Open the Dockerfile and make sure you understand what it does.

Try to build the image, run and inspect it. The goal is to figure out the size of the built container.

After you have found the size, change the Dockerfile to use multi-stage builds. The Dockerfile itself contains some hints on how to achieve that. Rebuild the image and compare the size to the original container.

What other benefits can you think of when using multi-stage containers?

## 3. Optional: Write it yourself

Open the exercise 3 [folder](templates/3) `templates/3`.

The small python programm you see, just prints the files from a directory you give as a parameter.

Open the Dockerfile in the folder.
You can see that there are comments describing what the direct line under it does.
There is also a small python file, which just prints all files of the directory given in the parameter.

Try to implement the Dockerfile and get it to run. If sucessfully built and ran, you should see some output in your console.

## 4. Solutions

You can find the solutions [here](solutions/): `solutions/`.

## Clean up

There are two possibilities to clean up the images after the exercises.

The first one is to list all images and use the rmi docker command.

```
docker images -a
docker rmi <image>
```

For the second one Docker provides a single command that will clean up any resources — images, containers, volumes, and networks — that are dangling (not associated with a container):

```
docker system prune
```

To additionally remove any stopped containers and all unused images (not just dangling images), add the -a flag to the command:

```
docker system prune -a
```


[Back to Overview](https://github.com/ninech/academy)
