# Step 2

The subject of this tutorial is DevOps and containairization. 
We will put this Rust server in a container and made it available online.

⚠️ The server will not be put on `Docker hub`!

Make a Docker file

touch Dockerfile{{execute}}

We will be running a Rust image, so go to Docker hub and check the Rust official image: https://hub.docker.com/_/rust.

** a note on rust:latest**
You usually don't want to do that but Rust is backward compatible.
Populate the Dockerfile:

`FROM`, aka the Docker image.

`WORKDIR` not necessary. The system assumes that we are in the current folder. This is the standard idiom for basically every CLI tool.

`RUN` cargo install --path ., as per the Docker hub documentation

`CMD` ["server_devops"]: this will comme as a command line argument.

`EXPOSE 7878`: the server will listen on port `7878`
