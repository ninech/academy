FROM golang:alpine
WORKDIR /app
ADD . /app
# creates the executable named goapp
RUN cd /app && go build -o goapp
ENTRYPOINT ./goapp

# If you run docker build on this file, you should notice that it is quite big. Especially for a small hello world app.
# Try to answer why the image is so big and write the size down. Google is your friend :D


# TODO: Refactor the above to be a multi-staged Dockerfile.

# In the first part of the multi staged build, you should try and build the executable from the the given hello.go file.
# You can use golang:alpine as a base. Remember this is a multi staged build.






# In the second part of the multi staged build, you should try and copy the executable and run it.
# You should use gcr.io/distroless/static as the second base. But why? Why is that base better than golang:alpine?
# You can find the docs here: https://github.com/GoogleContainerTools/distroless/blob/master/base/README.md & https://github.com/GoogleContainerTools/distroless
