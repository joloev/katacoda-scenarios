# Fix the Rust server to listen to the world

The Rust server is listening on localhost. But the localhost of the Container is not your localhost.

What is happening is something like this:

[ you @ 127.0.0.1 port 7878 ] ---> docker fuckery ---> [ you + container @ 172.17.0.2 port 7878 ]  ---> more docker fuckery ---> [ you + container @ fake 127.0.0.1 port 7777 ]

We are listening at an address that does not exist.

To fix this, go to the Rust code.

`nano src/main.rs`{{execute}}

and change the line:

```git
- let listener = TcpListener::bind("127.0.0.1:7878").unwrap();
+ let listener = TcpListener::bind("0.0.0.0:7878").unwrap();
```
Save the file.
The server will now listen to any computer, on port 7878.

Rebuild the file as per step3.

Run the file as per step 4. (if the old server is running, use `docker stop <Container name>`)

Go to `localhost:7777` and you should see:

![](./assets/easter_bunny.png)
