# Making a Docker compose file

## Docker compose

Some people will say you need several services to use a `docker-compose`. Don't listen to them :).

Wouldn't it be nice to run docker with all ports already configured? Isn't it annoying to run `docker run ...` and have to get the ports right every time?

Let's write all into a docker-compose file so we can run `docker-compose up` (with or without detached `-d` flag) and everything starts working; with the image already being built on-demand if needed.

MAKE THAT

touch docker-compose.yml

```
services:
    rusty:
        container_name: rusty-server1
        image: rusty-server
        ports:
            - "7777:7878"
        tty: true
```

## Environment variables in the docker compose

One big DevOps concept though is configuring through environment variables rather than hard coding things. So you could set the port number and hosting address via environment variables and then set those up with docker-compose if you wanted.

```
services:
    rusty:
        container_name: ${NAME}
        image: rusty-server
        ports:
            - "7777:7878"
        tty: true
```

You can now run

```
NAME=<your chosen name> docker-compose up
```

See with `docker ps -a`