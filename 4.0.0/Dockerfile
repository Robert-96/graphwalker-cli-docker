FROM debian:sid

RUN apt-get update && apt-get install -y \ 
    wget \
    openjdk-8-jdk \
    python3 \
    python3-pip \
    git

# Get the GraphWalker CLI jar
RUN wget https://github.com/GraphWalker/graphwalker-project/releases/download/LATEST-CLI/graphwalker-cli-4.0.0-SNAPSHOT.jar

# Create a script
RUN echo '#!/bin/bash\njava -jar /graphwalker-cli-4.0.0-SNAPSHOT.jar "$@"' >> /graphwalker-cli
RUN chmod +x graphwalker-cli

# Create a symbolic link 
RUN ln -s /graphwalker-cli /usr/bin/gw
