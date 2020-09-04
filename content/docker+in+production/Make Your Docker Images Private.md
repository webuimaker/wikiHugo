---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 4  # Order that this section will appear.
title: "Make Your Docker Images Private"
titleColor: ""
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
The way you create, host, and share your Docker images has a bearing on security. Docker images are hosted in a registry. This could be [Docker Hub](/display/containers/working+with+docker+hub), [Quay](https://www.aquasec.com/), [Artifactory](https://jfrog.com/artifactory/), or a host of other options. The important thing is to have a private registry. This way you protect yourself from infected or vulnerable container images that are spread around loosely in public from affecting your system.

Despite using a private container registry, you still need to scan every container image downloaded. Always prefer official images to unofficial ones. Scan images for commonly known vulnerabilities, as even official images may contain vulnerabilities. All private container registries include this feature by default, but to go a step further, tools like [Aqua Security](https://www.aquasec.com/) are able to scan images in a broader context, and with greater accuracy.