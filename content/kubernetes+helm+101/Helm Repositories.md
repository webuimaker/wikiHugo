---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 9  # Order that this section will appear.
title: "Helm Repositories"
titleColor: ""
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
A chart repository is a server that houses packaged charts. Any HTTP server that can serve YAML files and tar files can be used as a repository server. Helm does not provide tools for uploading charts to remote repository servers. 

A repository has a special file called `index.yaml` that lists all the packages, together with data that allows retrieving and verifying those packages.

On the client side, repositories are managed with the `helm repo` commands.


**For more details, see Helm Documentation:** {{< read-more "Repo Commands" "https://docs.helm.sh/helm/#helm-repo" "_target"  >}}