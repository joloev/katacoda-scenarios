# Step 3: Create a Docker container

- explain what a docker container is


1. Make a Dockerfile

`touch Dockerfile`{{execute}}
`nano Dockerfile`{{execute}}
Or VScode, or VIM


2. Populate the Dockerfile:
Reference: https://hub.docker.com/_/rust

`FROM`, aka the Docker image.
**A note on rust:latest**: You usually don't want to do that but Rust is backward compatible.

`WORKDIR` is NOT necessary. The system assumes that we are in the current folder. This is the standard idiom for basically every CLI tool.

`RUN` cargo install --path ., as per the Docker hub documentation

`CMD` ["server_devops"]: this will comme as a command line argument.

`EXPOSE 7878`: the server will listen on port `7878`


SOLUTION:

```
FROM rust:latest

COPY . .

RUN cargo install --path .

CMD ["server_devops"]

EXPOSE 7878
```{{copy}}

