# Set up Docker container running a rust server

## Why using Docker?

Docker is an open source containerization platform. Docker uses a linux kernel and takes advantage of several feature that comes with it such as namespaces and control groups.

Docker is important from a Devops perspective as it allows multiple applications and processes to share resources to make better use of the infrastructure yet keep them running seperatly retaining the security one would have using two seperate system. 

Docker also provide an image-based deployment model making it easier to share an application or service across multiple environments.

Furthermore, Docker automates deployment of the application within the container environment. 

More information can be found at [Docker's website](https://www.docker.com/)


## Rust server
Complete code for the rust server set up in this tutorial can be found at this [github repo](https://github.com/joloev/DD2482-executable-tutorial).

## Intended learning outcomes
- Learn how to set up a Docker container and a few basic Docker commands neccessary
- Learn how to deploy a rust server in using the Docker container