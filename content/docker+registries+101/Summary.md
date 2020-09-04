---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 7  # Order that this section will appear.
title: "Summary"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
A Docker registry is a system for versioning, storing and distributing Docker images. DockerHub is a hosted registry used by default when installing the Docker engine, but there are other hosted registries available for public use such as AWS and Google’s own registries.

It is also possible to host a registry on-premise for isolation and/or tighter integration with CI/CD workflows. Extensions to the open source Docker registry such as Docker’s own Trusted Registry or VMWare’s Harbor can help alleviate some of the operational burden of running a registry on-premise.

Image repositories inside a registry can be public (anyone can download them) or private (restricted access to the user or organization owning them).