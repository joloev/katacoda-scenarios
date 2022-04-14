# Step 4: Build and run the docker image

**Build the image**

Now lets build the customized image:

`docker build -t rusty-server .`{{execute}}

What happens is a new image, based on the Dockerfile will be built.

`-t` = tag, it allows us to name the Docker image. If not, it will be named `<none> `.

Check if the image has been created by running `docker images`{{execute}}. Do you see it?
<br/><br/>

**Run the image**

Now creating a container by running the customized docker image we built.

- `docker run -d -it --rm --name rusty-server1 rusty-server`{{execute}}

- `-d` also named `--detach` It will free your terminal after use and continue running it in the background, like the linux command `&`.

- `-it` are to seperate commands telling it should be in an interactive mode. `-i` means the command inside the container will be connected to the STDIN of the docker run itself and `-t` ensures the input of main process, inside docker is a terminal device.

- `--rm` automatically removes the container when it exits

- `--name` the syntax is : `--name <Container name> <Image>`

Run `docker ps -a`{{execute}} to list all the container running.



