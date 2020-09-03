---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 3  # Order that this section will appear.
title: "Image Registries"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
An [image registry](/display/containers/Container+Image+Registries) is a collection of private and/or public repositories to which users can upload and share their Docker images, as well as download (pull) images created by others. A repository is a collection of docker images with the same name but different tags (different versions, if you like).

Examples of public registries include:

* [Docker Hub](/display/containers/Working+With+Docker+Hub) , which contains both public and private repositories of images—the public repositories store images from community and official libraries.

* <strong>Quay </strong>, a hosted service which has a free plan for public repositories and a paid model for private repositories.

Cloud providers like [AWS](/display/containers/Containers+on+AWS) or [Google](/display/containers/Containers+on+Google+Cloud+Platform) typically provide their own registries as well.

Private repositories are suited for proprietary applications, for which you need to strictly control access to your container images.

It is possible to host a private registry composed only of private repositories, either on-prem or in the cloud. Examples include Gitlab’s Container Registry, or JFrog’s Artifactory.





**For further reading, see Docker Documentation:** {{< read-more "Image Registry"  "https://docs.docker.com/registry/"  "_blank"  >}}