---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 1  # Order that this section will appear.
title: "What is Docker Networking"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"

---

For [Docker containers](/display/containers/Docker+Containers) to communicate with each other and the outside world via the host machine, there has to be a layer of networking involved. Docker supports different types of networks, each fit for certain use cases.

For example, building an application which runs on a single Docker container will have a different network setup as compared to a web application with a cluster with database, application and load balancers which span multiple containers that need to communicate with each other. Additionally, clients from the outside world will need to access the web application container.

**See Docker Documentation:** {{< read-more "Network Containers" "https://docs.docker.com/engine/tutorials/networkingcontainers" "_blank"  >}}

## Docker Default Networking (docker0)

When Docker is installed, a default bridge network named  `docker0` is created. Each new Docker container is automatically attached to this network, unless a custom network is specified.

Besides  `docker0`  , two other networks get created automatically by Docker:  `host`  (no isolation between host and containers on this network, to the outside world they are on the same network) and  `none`            (attached containers run on container-specific network stack).

**See Docker Documentation:** {{< read-more "Default networks" "https://docs.docker.com/engine/userguide/networking/#default-networks" "_blank"  >}}


