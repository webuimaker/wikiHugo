---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 1  # Order that this section will appear.
title: "What is a Docker Registry"
titleColor: ""
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"

---
A <strong>Docker registry</strong> is a storage and distribution system for named [Docker](https://www.aquasec.com/wiki/display/containers/docker+containers) images. The same image might have multiple different versions, identified by their tags.

A Docker registry is organized into **[Docker repositories](/display/containers/docker+image+repositories)** , where a repository holds all the versions of a specific image. The registry allows Docker users to pull images locally, as well as push new images to the registry (given adequate access permissions when applicable).

By default, the Docker engine interacts with <strong>DockerHub</strong> , Docker's public registry instance. However, it is possible to run on-premise the open-source Docker registry/distribution, as well as a commercially supported version called <strong>Docker Trusted Registry</strong> . There are other public registries available online.

To pull an image from an on-premises registry, you could run a command similar to:


```docker pull my-registry:9000/foo/bar:2.1```


where you pull the version of ```foo/bar``` image with tag ```2.1``` from our on-premise registry located at ```my-registry``` domain, port ```9000``` .

If you used DockerHub instead, and 2.1 was also the latest version, you could run this command to pull the same image locally:

```docker pull foo/bar```



**For further reading, see Docker Documentation:** {{< read-more "About Registry"  "https://docs.docker.com/registry/introduction/" "_blank"  >}} and {{< read-more "Distribution"  "https://github.com/docker/distribution" "_blank"  >}}