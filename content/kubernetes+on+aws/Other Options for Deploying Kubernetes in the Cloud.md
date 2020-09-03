---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 6  # Order that this section will appear.
title: "Other Options for Deploying Kubernetes in the Cloud"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
Besides the Kubernetes deployment options already covered, there are other tools that can be used to deploy Kubernetes on public clouds like AWS. Each tool has its unique features and building blocks:



* [Heptio](https://github.com/heptio/aws-quickstart) - Heptio provides a solution based on CloudFormation and kubeadm to deploy Kubernetes on AWS, and supports multi-AZ. Heptio is suitable for users already familiar with CloudFormation AWS orchestration tool.

* [Kismatic Enterprise Toolkit (KET)](https://github.com/apprenda/kismatic) - KET is a collection of tools with sensible defaults which are production-ready to create enterprise-tuned clusters of Kubernetes. The goal with this toolkit is to make it easy for organizations to install and manage their Kubernetes infrastructure and clusters.

* [kubeadm](https://github.com/upmc-enterprises/kubeadm-aws) - The kubeadm project is focused on a solution to build a simple cluster on AWS using Terraform. It is an adequate tool for tests and proof-of-concepts only as it doesn’t support multi-AZ and other advanced features.

* [OpenShift](https://www.openshift.com/) - This is a Red Hat platform-as-a-service product for container-based deployment and management of software. There is an open source version called OpenShift Origin which adds developer and operations-centric tools on top of Kubernetes to enable rapid application development, easy deployment and scaling, and long-term lifecycle maintenance for small and large teams.

* [Stackpoint](https://stackpoint.io/) - This is a web based solution that provides a user friendly platform to provision Kubernetes on various cloud providers such as AWS, Google Cloud Platform, Microsoft Azure and Digital Ocean. This is a good tool for those using more than one cloud provider and would like a single place for managing their multi-cloud Kubernetes deployments.

* [Tack](https://github.com/kz8s/tack) - This is a terraform module that can be used to create Kubernetes clusters which run on any version of CoreOS on AWS. Supports multi-AZ deployments of worker nodes that are able to auto-scale.

* [Tectonic](https://github.com/coreos/tectonic-installer) - Tectonic enables an automated installation of Kubernetes with the goals of being secure by default, quick and easy to install clusters, highly available, modular and customizable. It also focuses on portability (runs on any operating system), and flexibility of deployment to multiple cloud providers such as AWS, Google Cloud Platform, or Microsoft Azur.


**For further reading, see Kubernetes Documentation:** {{< read-more "Discovering services" "https://kubernetes.io/docs/concepts/services-networking/service/#discovering-services" "_target"  >}}	
	