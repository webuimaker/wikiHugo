---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 5  # Order that this section will appear.
title: "Private Registries"
titleColor: ""
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
Use cases for running a private registry on-premise (internal to the organization) include:

* <strong>Distributing images</strong> inside an isolated network (not sending images over the Internet)

* <strong>Creating faster CI/CD pipelines</strong> (pulling and pushing images from internal network), including faster deployments to on-premise environments

* <strong>Deploying a new image</strong> over a large cluster of machines

* <strong>Tightly controlling where images are being stored</strong>

Running a private registry system, especially when delivery to production depends on it, requires operational skills such as ensuring availability, logging and log processing, monitoring, and security. Strong understanding of http and overall network communications is also important.

Some vendors provide their own extensions of the open source Docker registry. These can help alleviate some of the above operational concerns:

* **[Docker Trusted Registry](https://docs.docker.com/datacenter/dtr/2.4/guides/)** is Docker Inc’s commercially supported version, providing high availability via replication, image auditing, signing and security scanning, integration with LDAP and Active Directory.

* **[Harbor](https://github.com/vmware/harbor)** is a VMWare open source offering which also provides high availability via replication, image auditing, integration with LDAP and Active Directory.

* **[GitLab Container Registry](https://docs.gitlab.com/ce/administration/container_registry.html)** is tightly integrated with GitLab CI’s workflow, with minimal setup.

* **[JFrog Artifactory](https://www.jfrog.com/confluence/display/RTF/Getting+Started+with+Artifactory+as+a+Docker+Registry)** for strong artifact management (not only Docker images but any artifact).



**For further reading, see Docker Documentation:** {{< read-more "About Registry"  "https://docs.docker.com/registry/introduction/" "_blank"  >}}