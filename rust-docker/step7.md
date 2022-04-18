# Making a Docker compose file

## Docker compose

Some people will say you need several services to use a `docker-compose`. Don't listen to them :).

Wouldn't it be nice to run docker with all ports already configured? Isn't it annoying to run `docker run ...` and have to get the ports right every time?

Let's write all into a docker-compose file so we can run `docker-compose up` (with or without detached `-d` flag) and everything starts working; with the image already being built on-demand if needed.

In the same directory than the Dockerfile (`DD2482-executable-tutorial/server_devops/`), make a `docker-compose.yml` file.

`touch docker-compose.yml`{{execute}}.


Open `nano` and add this information to the file:

```
services:
    rusty:
        container_name: rusty-server1
        image: rusty-server
        ports:
            - "7777:7878"
        tty: true
```
A `yml` must be formatted correctly. You can use [a linter](http://www.yamllint.com/) if you encounter any errors.

## Environment variables in the docker compose

One big DevOps concept though is configuring through environment variables rather than hard coding. So you could set the port number and hosting address via environment variables and then set those up with docker-compose if you wanted! This allows flexibility and also making sure sensitive information are not leaked, as they are decided at runtime.

Try changing replacing the container name with an environment variable:

```
services:
    rusty:
        container_name: ${NAME}
        // ...
```

You can now run:

`NAME=<your-chosen-name> docker-compose up`{{execute}}

The variable <your-chosen-name> because visible to docker at runtime. You can of course replace any variable with an environment variable. You can try with the port.

See your new container name with `docker ps -a`{{execute}}.