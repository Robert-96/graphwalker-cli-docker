# graphwalker-cli-docker

Docker images for [GraphWalker CLI](http://graphwalker.github.io/).

## Supported tags and respective `Dockerfile` links

* [`4.3.2`, `latest` (Dockerfile)](https://github.com/Robert-96/graphwalker-cli-docker/blob/main/Dockerfile)

## GraphWalker CLI

[GraphWalker](http://graphwalker.github.io/) is an open source Model-Based testing tool for test automation. It's designed to make it easy to design your tests using graphs.

The GraphWalker command line interface is a tool for working with graphs.

## About this image

The `graphwalker-cli:latest` tag will always point the latest release (which is, at the time of this writing, `graphwalker-cli:4.3.2`).

Up to the `graphwalker-cli:4.2.0` tag all tags had installed OpenJDK 8 (because before version 4.3.0 the latest version of Java supported by GraphWalker was Java 8).

Beginning with the `graphwalker-cli:4.3.0` tag all tags will have installed OpenJDK 11.

## How to use this image

This image creates a script facilitating running GraphWalker's command line on a linux machine.

### Create a `Dockerfile` in your project

```dockerfile
FROM robert96/graphwalker-cli:latest
CMD gw online -s RESTFUL
```

Then, run the commands to build and run the Docker image:

```
$ docker build -t my-graphwalker .
$ docker run --name my-running-graphwalker -p 8887:8887 my-graphwalker
```

### Without a `Dockerfile`

Start the GraphWalker REST service on a docker image:

```
$ docker run -it -p 8887:8887 graphwalker-cli:latest gw online -s RESTFUL
```

Visit http://localhost:8887/graphwalker/getStatistics and you will see It works!

## License

This project is licensed under the [MIT License](https://github.com/Robert-96/graphwalker-cli-docker/blob/main/LICENSE).
