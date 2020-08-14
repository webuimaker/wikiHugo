---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 6  # Order that this section will appear.
title: "Common Operations"
titleColor: "#003366"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"

---

Some common operations you'll need with Docker images include:

- **Build a new image from a Dockerfile:** The command for building an image from a Dockerfile is  `docker build` , where you specify the location of the Dockerfile (it could be the current directory). You can (optionally) apply one or more tags to the resulting image using parameters. Use the `-t` option.
- **List all local images:** Use the `docker images` command to list all local images. The output includes image ID, repository, tags, and creation date.
- **Tagging an existing image:** You assign tags to images for clarification, so users know the version of an image they are pulling from a repository. The command to tag an image is `docker tag` and you need to provide the image ID and your chosen tag (including the repository). For example:
```java
docker tag 0e5574283393 username/my_repo:1.0
```
- **Pulling a new image from a Docker Registry:** To pull an image from a registry, use  `docker pull`  and specify the repository name. By default, the latest version of the image is retrieved from the Docker Hub registry, but this behaviour can be overridden by specifying a different version and/or registry in the pull command. For example, to pull version 2.0 of my_repo from a private registry running on localhost port 5000, run:
```
docker pull localhost:5000/my_repo:2.0
```
- **Pushing a local image to the Docker registry:** You can push an image to Docker Hub or another registry to make it available for other users by running the `docker push` command. For example, to push the (latest) local version of my_repo to Docker Hub, make sure you’re logged in first by running `docker login`, then run:
```
docker push username/my_repo
```
- **Searching for images:** You can search the Docker Hub for images relating to specific terms using `docker search`.  You can specify filters to the search, for example only list “official” repositories.