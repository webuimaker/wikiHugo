---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 2  # Order that this section will appear.
title: "DockerHub"
titleColor: ""
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---

[DockerHub](http://dockerhub.com/) is a hosted registry solution by Docker Inc. Besides public and private repositories, it also provides automated builds, organization accounts, and integration with source control solutions like [Github](https://github.com/) and [Bitbucket](https://bitbucket.org/) .

A public repository is accessible by anyone running Docker, and image names include the organization/user name. For example, ```docker pull jenkins/jenkins``` will pull the Jenkins CI server image with tag ```latest``` from the Jenkins organization. There are hundreds of thousands public images available. Private repositories restrict access to the repository creator or members of its organization.

DockerHub supports official repositories, which include images verified for security and best practices. These do not require an organization/user name, for example ```docker pull nginx```will pull the `l``atest``` image of the Nginx load balancer.

DockerHub can perform automated image builds if the DockerHub repository is linked to a source control repository which contains a build context (Dockerfile and all any files in the same folder). A commit in the source repository will trigger a build in DockerHub.





**For further reading, see Docker Documentation:** {{< read-more "Configure automated Docker builds"  "https://docs.docker.com/docker-hub/builds/" "_blank"  >}}




DockerHub can also automatically scan images in private repositories for vulnerabilities, producing a report detailing vulnerabilities found in each image layer, by severity (critical, major or minor).



**For further reading, see Docker Documentation:** {{< read-more "Docker Security Scanning"  "https://docs.docker.com/docker-cloud/builds/image-scan/" "_blank"  >}}


Note that multiple private repos, parallel builds and image security scanning are only available with paid subscriptions.




**For further reading, see Docker Documentation:** {{< read-more "Overview of Docker Hub"  "https://docs.docker.com/docker-hub" "_blank"  >}}







