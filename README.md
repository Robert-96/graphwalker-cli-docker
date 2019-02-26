# graphwalker-cli-docker

Docker images for GraphWalker CLI

## Supported tags and respective `Dockerfile` links

* [`4.0.0`, `latest` (4.0.0/Dockerfile)](https://github.com/Robert-96/graphwalker-cli-docker/blob/master/4.0.0/Dockerfile)
* [`3.4.2` (3.4.2/Dockerfile)](https://github.com/Robert-96/graphwalker-cli-docker/blob/master/3.4.2/Dockerfile)

## GraphWalker CLI

[GraphWalker](http://graphwalker.github.io/) is an open source Model-Based testing tool for test automation. It's designed to make it easy to design your tests using graphs.

The GraphWalker command line interface is a tool for working with graphs.

## How to use this image

This image creates a script facilitating runnig GraphWalker's command line on a linux machine.

### Create a `Dockerfile` in your project

```
FROM robert96\graphwalker-cli:latest
CMD gw online -s RESTFUL 
```

Then, run the commands to build and run the Docker image:

```
$ docker build -t my-graphwalker .
$ docker run --name my-running-graphwalker -p 8887:8887 my-graphwalker
```

### Without a Dockerfile

Start the GraphWalker REST service on a docker image:

```
docker run -it -p 8887:8887 graphwalker-cli:latest gw online -s RESTFUL
```

Visit http://localhost:8887/graphwalker/getStatistics and you will see It works!
