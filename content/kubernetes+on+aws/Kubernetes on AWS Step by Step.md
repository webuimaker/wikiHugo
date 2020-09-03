---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 2  # Order that this section will appear.
title: "Kubernetes on AWS Step by Step"
titleColor: ""
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---


In this article we provide step-by-step instructions for several common ways to set up a Kubernetes cluster on AWS:

* <strong>Creating a cluster with kobs </strong>- kops is a production-grade tool used to install, upgrade and manage Kubernetes on AWS. It supports Ubuntu, Debian, CentOS and RHEL, can generate Terraform templates, supports custom Kubernetes add-ons. [Learn more](#KubernetesonAWS-Kops)

* <strong>Creating a cluster with Amazon Elastic Kubernetes Service (EKS)</strong> - the managed Kubernetes service provided by Amazon. You can create a Kubernetes cluster with EKS using the AWS Management Console. [Learn more](#KubernetesonAWS-EKS)

* <strong>Creating a cluster with Rancher </strong>- Rancher is a Kubernetes management platform that eases deployment of Kubernetes and containers. It provides a convenient UI and integrates with LDAP, AD, and GitHub. Rancher runs on RancherOS, which is available as an AMI that can be deployed on any EC2 instance. [Learn more](#KubernetesonAWS-Rancher)

* <strong>Creating a cluster with Terraform</strong> - Terraform is an infrastructure-as-code tool that can deploy containerized applications into an properly configured Kubernetes cluster running in AWS. [Learn more](#KubernetesonAWS-Terraform)

* <strong>Other ways to deploy Kubernetes on AWS</strong> - we briefly review other tools you can use, including Heptio, kubeadm, and OpenShift. [Learn more](#KubernetesonAWS-Other)
---
























