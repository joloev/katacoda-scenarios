
Great job! You have successfully containerized a rust server using docker.

## What's next?
In this tutorial the entire application consists of a server. However, you might want to separate different parts of an application into different containers. For example, if you have an application with both a client and a server you may want two separate containers, one for the client and one for the server part. Docker-compose lets you do this smoothly. If you are interested in how it works you can read more about it in the [documentation](https://docs.docker.com/compose/)
 
If you want to make more servers in Rust, we recommend [Actix](https://actix.rs/). Their [examples](https://github.com/actix/examples) repo has everything you need to get you started.