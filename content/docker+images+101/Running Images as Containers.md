---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 2  # Order that this section will appear.
title: "Running Images as Containers"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
Images and containers are not the same—a container is a running instance of an image. A single image can be used to start any number of containers. Images are read-only, while containers can be modified, Also, changes to a container will be lost once it gets removed, unless changes are committed into a new image.

Follow these steps to run an image as container:

* First, note that you can [run docker container](/display/containers/Running+Docker+Containers) specifying either the image name or image ID (reference).

* Run the  `docker images`  command to view the images you have pulled locally or, alternatively,  [explore the Docker Hub](https://hub.docker.com/explore/)  repositories for the image you want to run the container from.

Once you know the name or ID of the image, you can [start a docker container](/display/containers/Starting+and+Restarting+Docker+Containers+Automatically) with the   `docker run`   command. For example, to download the Ubuntu 16.04 image (if not available locally yet), start a container and run a bash shell:
Once you know the name or ID of the image, you can [start a docker container](/display/containers/Starting+and+Restarting+Docker+Containers+Automatically) with the   `docker run`   command. For example, to download the Ubuntu 16.04 image (if not available locally yet), start a container and run a bash shell:

`docker run -it ubuntu:16.04 /bin/bash`




**For further reading, see Docker Documentation:** {{< read-more "Docker Run Reference"  "https://docs.docker.com/engine/reference/run/"  "_blank"  >}}