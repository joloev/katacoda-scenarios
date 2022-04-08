# Step 2: Set up Docker image

- explain what a docker image is: image == blueprint, container == made from blueprint

1. Go to Docker hub

We will be running a Rust image, so go to Docker hub and check the Rust official image: https://hub.docker.com/_/rust.

`docker pull rust`{{execute}}


Check the image arrived:

`docker image ls`{{execute}}

At time of creation

```console
REPOSITORY               TAG       IMAGE ID       CREATED             SIZE
rust                     latest    5593c6ce4c4e   18 hours ago        1.3GB

```


To list your images:

`docker images -a`

To remove an image:

`docker image rm [image name or image id]`
