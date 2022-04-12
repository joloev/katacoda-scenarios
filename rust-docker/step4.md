# Create the Dockerfile

Before instantiating the container we need to create the Dockerfile which defines which base image should be used and what other commands the docker container should run and where it should run it these commands.

Create a new Dockerfile in correct folder by typing
`cd DD2482-executable-tutorial/server_devops`{{execute}}
 `touch Dockerfile`{{execute}} make sure the naming is eactly as written here.

Open it in a text editor like `vim Dockerfile`{{execute}}
Change to insert mode `i`{{execute}}
Add the following in the file:

`FROM rust:latest`{{execute}}

`COPY . .`{{execute}}

`RUN cargo install --path .`{{execute}}

`CMD ["server_devops"]`{{execute}}

`EXPOSE 7878`{{execute}}

To save the file press `esc` to escape the insert mode and `:wq`{{execute}} to save the changes.

Each line of the Dockerfile creates a new read-only layer in the docker image. Let's go through them one by one.

`FROM`, aka the Docker image. This is the parent or base image which our customized image will be built upon.
A note on **rust:latest**: You usually don't want to use the tag *latest*, but Rust is backward compatible.

`WORKDIR` is NOT necessary. The system assumes that we are in the current folder.  This sets the working directory for the image where the following commands like RUN, CMD, etc.. will be executed.

`RUN` cargo install --path ., as per the Docker hub documentation

`CMD` ["server_devops"]: specifies that the command server_devops should be executed when running a container. 

`EXPOSE 7878`: means server will listen on port `7878`.

