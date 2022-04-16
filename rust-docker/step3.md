# Pull a base image from Docker Hub

Unlike the picture showed in step 1. We will first make sure we have a base image before we create the Dockerfile.
In order to run the Rust server inside the Docker container, we are about to create, we need an docker image which allows us to run Rust programs inside the Docker container. Luckily there is already a predefined we can download: you can check Rust official image [on Docker hub](https://hub.docker.com/_/rust).

Run `docker pull rust`{{execute}}
This may take a a few minutes.

Check that the image has been succesfully downloaded by running 
`docker images`{{execute}}

This command will list all local images. We have been downloading a *layer* on which we will build our personalized docker image.

You should now see the following information in the terminal:

```
REPOSITORY               TAG       IMAGE ID       CREATED             SIZE
rust                     latest    5593c6ce4c4e   <time>             1.3GB
```

To remove an image run `docker image rm [image name or image id]`
