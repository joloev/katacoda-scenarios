# Create a Docker container

As mentioned earlier docker container is based on a Docker image, which sets the structure and requirments of the container. 

A docker container are a virtualized environment which allows for an application to be isolated from other applications yet using the same host system.

1. Make a Dockerfile
`cd DD2482-executable-tutorial/server_devops`{{execute}}
Create a new Dockerfile `touch Dockerfile`{{execute}} make sure the naming is eactly as written here.

Open it in a text editor like `vim Dockerfile`{{execute}}
Change to insert mode `i`{{execute}}
Add the following in the file

`FROM rust:latest`{{execute}}
`COPY . .`{{execute}}
`RUN cargo install --path .`{{execute}}
`CMD ["server_devops"]`{{execute}}
`EXPOSE 7878`{{execute}}

Here is an explanation of what a typical Dockerfile requires:

`FROM`, aka the Docker image.
**A note on rust:latest**: You usually don't want to use tag latest but Rust is backward compatible.

`WORKDIR` is NOT necessary. The system assumes that we are in the current folder. This is the standard idiom for basically every CLI tool.

`RUN` cargo install --path ., as per the Docker hub documentation

`CMD` ["server_devops"]: this will come as a command line argument.

`EXPOSE 7878`: means server will listen on port `7878`


