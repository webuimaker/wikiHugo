---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 2  # Order that this section will appear.
title: "Security"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
Security is the first priority when running containers in production. However, there isn’t a single do-it-all tool, instead, you need to use a combination of tools.


## Kernel Security Tools

Docker has borrowed core Linux kernel security features like namespaces, cgroups, apparmor, SELinux, and SecComp. These features provide the first and most foundational layer of security for containers.


**Read:** {{< read-more "Overview of Linux Kernel Security Features"  "https://www.linux.com/learn/overview-linux-kernel-security-features" "_blank"  >}}

## Project Calico

Securing network connections is essential for containers. This is achieved by Calico, a tool that creates micro-firewalls around each containerized service and provides granular security controls.


**Get started with** {{< read-more "Project Calico"  "https://www.projectcalico.org/" "_blank"  >}}

## Vault

Coming from the house of HashiCorp, creators of the popular Terraform scheduler, Vault is a secrets management tool for containers. Vault stores and encrypts secret data on physical storage and requires multiple keys to access and read the secrets. Vault simplifies secrets management and makes it more powerful.


**Get started with** {{< read-more "Vault"  "https://learn.hashicorp.com/vault/getting-started/first-secret" "_blank"  >}}

## Aqua Security

In production, containers need to be shielded from outside attacks and internal configuration lapses. This kind of threat detection is done using a proactive security tool like Aqua Security. It is able to track every part of the container stack and leverages machine learning to spot threats at any stage.


**Get started with** {{< read-more "Aqua"  "https://www.aquasec.com/" "_blank"  >}}