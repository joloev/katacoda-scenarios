# Clone the rust server

A Rust server has been created beforehand, as this tutorial won't cover how to build the server itself. In order to make it run inside the Docker container we need to clone it from Github.
<br/><br/>

Run `git clone https://github.com/joloev/DD2482-executable-tutorial.git`{{execute}} to get a local copy of the rust server.


## Overview of Rust server
Before getting started we will briefly introduce how the rust server works. 

<!-- TO DO: exlpain the main function and handle_connection-->
The main function will listen to incoming connections on localhost:

```rust
listener = TcpListener::bind("127.0.0.1:7878");
```

In case of success, function `handle_connection` will return a simple `html` page that you can see in your webbrowser.

This is the simplest example possible. As you may know, most people using a server do not write those from scratch, and we will put some links if you are interested into writing Rust servers in our conclusions.

This code is available [here](https://github.com/joloev/DD2482-executable-tutorial).
For more information on Rust visit 
https://doc.rust-lang.org/book/


