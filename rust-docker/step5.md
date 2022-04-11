# Step 4: Build and run the docker image

1. build
An image is like a blue print of the application (the container)

`docker build . -t rusty-server`

*explain what build does*

`-t` = tag, it allows us to tag the Docker image. If not, it will be tagged `<none> `.

Check if the image has been created:

`docker image ls`{{execute}}, you should see it.

2. run

Run the docker image:
`docker run -d -it --rm --name rusty-server1 rusty-server`

The flags are:
`-d` detached mode, it will free your terminal after use. Like `&` in the background.
`-it` Interractive mode
`--name` the syntax is : `--name <Container name> <Image>`

You should see the container with `docker ps -a`


