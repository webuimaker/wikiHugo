---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 4  # Order that this section will appear.
title: "Common Operations Using DockerHub"
titleColor: ""
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---

Common operations using DockerHub include:

* <strong>Login to DockerHub:</strong> Running `docker login` will ask for your DockerHub ID and password.

* **Searching for an image in a public repository**:  Use the ```docker search``` command with a search term to find all images in public (including official) repositories that match that term.

* <strong>Pulling an existing image:</strong> Use ```docker pull``` and specify the image name. By default, the latest version is retrieved, but this behavior can be overridden by specifying a different image tag/version. For example, to pull the (older) version 14.04 of the Ubuntu image:

```
docker pull ubuntu:14.04
```

* <strong>Pushing a local image:</strong> You can push an image by running the `docker push` command. For example, to push the (latest) local version of my-image to my registry:

```
docker push my-username/my-image``
```

* <strong>Create a new organization:</strong> This must be done from a browser . Go to [DockerHub](http://dockerhub.com/) , click <strong>Organizations</strong> and then click <strong>Create Organization</strong> and fill in the required data.

* <strong>Creating a new repository:</strong> This must be done from a browser . Go to [DockerHub](http://dockerhub.com/) , click the <strong>Create</strong> drop-down and select <strong>Create Repository</strong>. Fill in the required data. You will now be able to start pushing images to this repository.

* <strong>Create an automated build:</strong> This must be done from a browser . First, link your Github or Bitbucket account to [DockerHub](http://dockerhub.com/) , by navigating to your profile settings, then click <strong>Linked Accounts & Services</strong> . Select <strong>Public and Private</strong> access (mandatory) and authorize.  Then, click the <strong>Create</strong> drop-down, select <strong>Create Automated Build</strong> and select which source repository you want to build images from. 




**For further reading, see Docker Documentation:** {{< read-more "Overview of Docker Hub"  "https://docs.docker.com/docker-hub" "_blank"  >}},{{< read-more "Repositories on Docker Hub"  "https://docs.docker.com/docker-hub/repos/" "_blank"  >}}, and {{< read-more "Configure automated builds on Docker Hub"  "https://docs.docker.com/docker-hub/builds/" "_blank"  >}},