---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 3  # Order that this section will appear.
title: "Other Public Registries"
titleColor: ""
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
Other companies host paid online Docker registries for public use. Cloud providers like AWS and Google, who also offer container-hosting services, market the high availability of their registries.

* **[Amazon Elastic Container Registry (ECR)](https://aws.amazon.com/ecr/)** integrates with AWS Identity and Access Management (IAM) service for authentication. It supports only private repositories and does not provide automated image building.

* **[Google Container Registry (GCR)](https://cloud.google.com/container-registry/)** authentication is based on Google’s Cloud Storage service permissions. It supports only private repositories and provides automated image builds via integration with Google Cloud Source Repositories, GitHub, and Bitbucket.

* **[Azure Container Registry (ACR)](https://azure.microsoft.com/en-us/services/container-registry/)** supports multi-region registries and authenticates with Active Directory. It supports only private repositories and does not provide automated image building.

* **[CoreOS Quay](https://quay.io/)** supports OAuth and LDAP authentication. It offers both (paid) private and (free) public repositories, automatic security scanning and automated image builds via integration with GitLab, GitHub, and Bitbucket.

* **[Private Docker Registry](https://private-docker-registry.com/)** supports OAuth, LDAP and Active Directory authentication. It offers both private and public repositories, free up to 3 repositories (private or public).

