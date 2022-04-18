# Making a Docker compose file

## Docker compose

When learning how to use docker it is important to also get familiarized with Docker compose.
Docker Compose lets you configure and run multiple containers from different images using one command.
All you need to add is a YAML file named `docker-compose.yml` to run all your services in one single command.
 
However, you need not necessarily have several services in order to use a `docker-compose`. One is enough.
Notice in the previous step we had to set the ports everytime we ran `docker run ...`
 
Wouldn't it be nice to run docker with all ports already configured? Let's change it.
 
Let's configure all ports inside the docker-compose file so we can run `docker-compose up` (with or without detached `-d` flag) and everything starts working; with the image already being built on-demand if needed.
 
Go to the same folder the Dockerfile is placed. `cd /root/DD2482-executable-tutorial/server_devops/`{{execute}}
In the same directory as the Dockerfile (`DD2482-executable-tutorial/server_devops/`), create a `docker-compose.yml` file.

`touch docker-compose.yml`{{execute}}.

Open it in a text editor like `vim docker-compose.yml`{{execute}}
Change to insert mode `i`{{execute}}
Add the following in the file:

```
services:
    rusty:
        container_name: rusty-server1
        image: rusty-server
        ports:
            - "7777:7878"
        tty: true
```

To save the file press `esc` to escape the insert mode and `:wq`{{execute}} to save the changes.
 
Notice a `yml` must be formatted correctly. You can use [a linter](http://www.yamllint.com/) if you encounter any errors.
 
 
## Environment variables in the docker compose
 
One big DevOps concept is configuring through environment variables rather than hard coding. For example you may set the port number and hosting address via environment variables when using docker-compose. This allows flexibility and also making sure sensitive information is not leaked, as they are decided at runtime.
 
Lets rewrite the YAML file to enable the container name to be chosen at runtime.
 
Open the YAML file in a text editor again, `vim docker-compose.yml`{{execute}}
Change to insert mode `i`{{execute}}
Change the line defining the container name to the following:
 
```
services:
   rusty:
       container_name: ${NAME}
       // ...
```
 
 
To save the file press `esc` to escape the insert mode and `:wq`{{execute}} to save the changes.
 
 
You can now run:
 
`NAME=<your-chosen-name> docker-compose up`{{execute}}
 
The variable <your-chosen-name> becomes visible to docker at runtime. You can of course replace any variable with an environment variable. You can try with the port.
 
See your new container name with `docker ps -a`{{execute}}.