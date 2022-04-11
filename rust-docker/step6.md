# Fix the Rust server to listen to the world

## A first try

What about this port we created? We need to make it available from to the outside world!

You need to stop your running container with

`docker stop <Container name>`

If you run `docker ps -a`, the container should have been removed, thanks to the flag `--rm`.

Re-run the previous command but this time exposing the port. Choose a port, we chose `7777`. `7878` is the port we chose for the Rust server in the Rust code.

(put rust code here?)

`docker run -d -it -p 7777:7878 --rm --name rusty-server1 rusty-server`{{execute}}

`docker ps -a` will show you:

```console
CONTAINER ID   IMAGE     COMMAND           CREATED          STATUS          PORTS                                       NAMES
5be3e4655dd5   servo     "server_devops"   31 seconds ago   Up 30 seconds   0.0.0.0:7777->7878/tcp, :::7777->7878/tcp   servo1
```
Meaning that requests to 7777 will be redirected to 7878.

This is not working, why??

See that on next page.

