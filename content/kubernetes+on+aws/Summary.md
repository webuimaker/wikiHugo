---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 10  # Order that this section will appear.
title: "Summary"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
AWS is a premiere solution for running cloud native apps, but setting up Kubernetes to run on it can be complex. This is where Kubernetes deployment tools like Kops come in. Amazon itself offers alternatives to decrease the operational overhead of setting up Kubernetes: on one hand there’s the Elastic Container Service (ECS) which is a container orchestration service focused on high availability (HA) out-of-the-box but is not portable to other infrastructure providers. There’s also the Amazon Elastic Container Service for Kubernetes (EKS) which is compatible with existing Kubernetes configurations and provides HA across availability zones by default. Rancher and Terraform are tools than can help accelerate deployment of applications in Kubernetes clusters. Rancher’s forte is their application catalog that allows deploying standard and custom applications with a few clicks. Terraform can be useful for adopting a unified infrastructure configuration language across providers.