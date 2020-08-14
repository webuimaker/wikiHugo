---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 3  # Order that this section will appear.
title: "DOCKER IMAGES"
titleColor: 
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---


## What is a Docker Image?

A {{< target-blank "Docker" "https://www.aquasec.com/wiki/display/containers/Docker+Containers"  >}}  image is a snapshot, or template, from which new containers can be started. It’s a representation of a filesystem plus libraries for a given OS. A new image can be created by executing a set of commands contained in a Dockerfile (it’s also possible but not recommended to take a snapshot from a running container). For example, this  Dockerfile  would take a base Ubuntu 16.06 image and install mongoDB, resulting in a new image:

```java
FROM ubuntu:16.04
RUN apt-get install -y mongodb-10gen
```

From a physical perspective, an image is composed of a set of read-only layers. Image layers function as follows:

- Each image layer is the outcome of one command in the image’s Dockerfile—an image is then a compressed (tar) file containing the series of layers.

- Each additional image layer only includes the set of differences from the previous layer (try running  `docker history`  for a given image to list all its layers and what created them).

**For further reading, see Docker Documentation:** {{< read-more "About images, containers, and storage drivers" "https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/" "_blank" >}}

