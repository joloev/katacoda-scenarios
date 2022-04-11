# Step 4: Build and run the docker image

Now lets build the customized image:

`docker build . -t rusty-server`{{execute}}

What happens is a new image, based on Dockerfile created we be built.

`-t` = tag, it allows us to tag the Docker image. If not, it will be tagged `<none> `.

Check if the image has been created by running `docker images`{{execute}}. Do you see it?

Now create a container based by running the customized docker image.

`docker run -d -it --rm --name rusty-server1 rusty-server`{{execute}}

`-d` detached mode, it will free your terminal after use. Like `&` in the background.
`-it` Interractive mode
`--name` the syntax is : `--name <Container name> <Image>`

Run `docker ps -a`{{execute}} to see that the container is up and running.


