FROM debian:buster

RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y \
    wget \
    openjdk-11-jdk

# Get the GraphWalker CLI jar
RUN wget https://github.com/GraphWalker/graphwalker-project/releases/download/4.3.0/graphwalker-cli-4.3.0.jar

# Create a script
RUN echo '#!/bin/bash\njava -jar /graphwalker-cli-4.3.0.jar "$@"' >> /graphwalker-cli
RUN chmod +x graphwalker-cli

# Create a symbolic link
RUN ln -s /graphwalker-cli /usr/bin/gw
