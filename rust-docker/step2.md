# Step 2: Set up Docker image

## What is a Docker image?
Now when we have a brief understanding of the rust server itself and the code used for it is time to start building the Docker container. Docker is an image based tool. This means one can create a sort of template for how a Docker container should look like. This teplate can then be reused when initialising new docker container. 

If you are familiar with object oriented programming you can compare Docker image being a class and a docker container an instance of a class.

There are multiple predefined Docker images you can download from [Docker Hub](https://hub.docker.com/)

If you have installed Docker you can download the predifned Docker images in the terminal using the docker command, see example below.

## Download a premade docker image

In order to run the rust server inside the Docker container, we are about to set up, we need animage which allows us to run rust programs inside the Docker container. Luckily there is already a predefined we can download.

Run `docker pull rust`{{execute}}
This may take a a few minutes.

Check that the image has been succesfully downloaded by running 
`docker images`{{execute}}
This command will list all local images.

You should now see the following information in the terminal:

```console
REPOSITORY               TAG       IMAGE ID       CREATED             SIZE
rust                     latest    5593c6ce4c4e   <time>             1.3GB

```

To remove an image run `docker image rm [image name or image id]`
