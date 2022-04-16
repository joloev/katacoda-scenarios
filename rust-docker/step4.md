# Create the Dockerfile

We could have skipped the first step `docker pull` to get the official Rust image. The first line, `FROM` will download the image from Docker hub if we don't have it on our system. 
The Rust official image will be the first layer of our Dockerfile. We will add additional layers while we customizing in following lines.

## Creating the Dockerfile

Before instantiating the container we need to create the Dockerfile which defines which base image (first layer) should be used and what other commands (additional layers) the docker container should run and where it should run it these commands.

Create a new Dockerfile in correct folder by typing
`cd DD2482-executable-tutorial/server_devops`{{execute}}

`touch Dockerfile`{{execute}} make sure the naming is exactly as written here.

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

A note on **rust:latest**: You usually don't want to use the tag *latest*, but one of the strengths of Rust is to backward compatible. You are not stuck to with a specific version, aka, no breaking changes!

`WORKDIR` (as per the official [Docker Hub Rust](https://hub.docker.com/_/rust)  documentation) **is NOT** necessary. The system assumes that we are in the current folder and sets it the working directory. The following commands like `RUN`, `CMD`, etc. will be executed here.

`RUN` cargo install --path ., as per the Docker hub documentation. This will make an executable file called `server_devops`. If you are unfamiliar with Rust, the name of the executable file is the same as the name of the package. You can find this information in the `Cargo.toml` file.

```rust
[package]
name = "server_devops"
```

`CMD` ["server_devops"]: specifies that the command server_devops should be executed when running a container. 

`EXPOSE 7878`: means server will listen on port `7878`.

