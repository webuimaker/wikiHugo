---
# Accomplishments widget.
widget: "reading"  # See https://sourcethemes.com/academic/docs/page-builder/
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 5 # Order that this section will appear.
title: "Further Reading"
subtitle: ""

# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"

# Accomplishments.
#   Add/remove as many `[[item]]` blocks below as you like.
#   `title`, `organization` and `date_start` are the required parameters.
#   Leave other parameters empty if not required.
#   Begin/end multi-line descriptions with 3 quotes `"""`.
itemLink:

---

- **[Installing Kubernetes](/display/containers/installing+kubernetes)**  —There are many ways to install Kubernetes Guide and the obvious starting point is the&nbsp;setup&nbsp;section, but the installation process can sometimes be a challenge. This page gathers resources about how to install Kubernetes on various environments like Ubuntu, Windows and CentOS.

- **[Kubernetes Configuration](/display/containers/kubernetes+configuration)**  — Kubernetes Guide reads&nbsp;YAML&nbsp;files to configure services, pods and replication controllers.This page gathers resources about working with the Kubernetes configuration to deploy containers.

- **[Kubernetes Monitoring](/display/containers/kubernetes+monitoring)**  — Monitoring Kubernetes effectively requires to rethink and reorient all monitoring strategies, especially if using traditional hosts such as VMs or physical machines. This page gathers resources about how to monitor Kubernetes cluster with tools like Prometheus and Datadog.

- **[Kubernetes Debugging and Troubleshooting ](/display/containers/kubernetes+debugging+and+troubleshooting)**  — Resources about the process of managing and maintaining production-grade, highly available Kubernetes clusters, including Kubernetes security, Kubernetes networking, Kubernetes load balancing and more.

- **[Kubernetes Load Balancing](/display/containers/kubernetes+load+balancing )**  — Load balancing is a relatively straightforward task in many non-container environments, but it involves a bit of special handling when it comes to containers. There are two different types of load balancing in Kubernetes - Internal load balancing across containers of the same type using a label, and external load balancing. This page gathers resources about how to configure and use the Kubernetes load balancer feature.

- **[Kubernetes Security](https://www.aquasec.com/solutions/kubernetes-container-security/)**  — Kubernetes Guide provides many controls that can improve application security. Configuring them requires intimate knowledge with Kubernetes and the deployment’s security requirements.&nbsp;This page gathers resources about security best practices for Kubernetes, including best practices for deployment, sharing data and network security.

- **[Kubernetes Networking](/display/containers/kubernetes+networking+101)**  — Kubernetes does not provide any default network implementation, rather it only defines the model and leaves to other tools to implement it. There are many implementations nowadays like Flannel,&nbsp;Calico&nbsp;and&nbsp;Weave. This page gathers resources about how to set up highly available networked Kubernetes clusters.

- **[Kubernetes Storage Management](/display/containers/kubernetes+storage+management)**  —  Kubernetes is complex, and difficult to set up and configure. The best approach, therefore, is to seek out a complete container solution that includes Kubernetes as a supported, maintained component. This page gathers resources about the leading Kubetnetes distributions such as OpenShift, Canonical, Rancher and more.

- **[Kubernetes in Production](/display/containers/kubernetes+in+production)**  —  The default configurations for Kubernetes Guide components are not designed for heavy and dynamic production workloads, characteristic of DevOps environments and micro-services based application deployments where containers are quickly created and destroyed.&nbsp;This page gathers resources about how to create a production-ready Kubernetes cluster, including examples and tutorials.

- **[Working with Kubernetes Ingress](/display/containers/working+with+kubernetes+ingress)**  —  Kubernetes ingress is a collection of routing rules that govern how external users access services running in a Kubernetes cluster. &nbsp;This page will introduce general strategies in Kubernetes for ingress, tutorials on how to build and troubleshoot Kubernetes Ingress controller and more.

- **[Kubernetes Security Best Practices](/display/containers/kubernetes+security+best+practices)**  — Kubernetes deployments have opened up a new set of infrastructure security  https://blog.aquasec.com/managing-kubernetes-secretsconcerns for development and operations teams. This page gathers resources about things you need to know about securing your Kubernetes infrastructure.

- **[Managing Kubernetes with Kops and Kubeadm](/display/containers/managing+kubernetes+with+kops+and+kubeadm)**  — Kops and Kubeadm is an official Kubernetes project for managing production-grade Kubernetes clusters.&nbsp;This Page gathers resources about Kops and Kubeadm basics and tutorials, including how to deploy Kubernetes on AWS.

- **[Kubernetes Secrets](/display/containers/kubernetes+secrets)**  — Kubernetes Secrets https://blog.aquasec.com/managing-kubernetes-secrets are objects used to control access within the Kubernetes container-orchestration system. This page gathers resources about the nature of Kubernetes Secrets, how you can use them, and related tools and products.

- **[Kubernetes Autoscaling](/display/containers/kubernetes+autoscaling)**  — Kubernetes Autoscaling is a feature for scaling nodes and pods in a Kubernetes Cluster. Autoscaling tools include Cluster Autoscaler and Horizontal Pod Autoscaler (HPA). While the scaling is automated, setting it up requires human involvement. This page gathers resources about autoscaling in Kubernetes.

- **[Kubernetes ConfigMap](/display/containers/kubernetes+configMap)**  — The ConfigMap API resource provides mechanisms to inject containers with configuration data while keeping containers agnostic of Kubernetes. ConfigMap can be used to store fine-grained information like individual properties or coarse-grained information like entire config files or JSON blobs. This page gather&nbsp;resources about Kubrenetes ConfigMap and how to create and use it.

- **[Kubernetes Namespace](/display/containers/kubernetes+namespace)**  — Kubernetes uses a concept called namespaces to help address the complexity of organizing objects within a cluster. Namespaces allow you to group objects together so you can filter and control them as a unit.&nbsp;This page gather resources about Kubrenetes namespace and how to use namespaces to manage your Kubernetes objects.

- **[Kubernetes Authentication](/display/containers/kubernetes+authentication)**  — Kubernetes offers a variety of authentication strategies including: client certificates, OpenID Connect Tokens, Webhook Token Authentication, Authentication Proxy, Service Account Tokens, and several more. This page gather&nbsp;resources&nbsp; about&nbsp;Kubernetes authentication and how to configure it.

- **[Kubernetes Vault](/display/containers/kubernetes+vault)**  — Vault is a tool for managing sensitive data like passwords, access keys, and certificates. Vault allows us to decouple secrets from applications.&nbsp;&nbsp;Vault has built-in support for Kubernetes and can use Kubernetes APIs to verify the identity of an application. This page gather&nbsp;resources about Kubernetes Vault and how to use it.

- **[CIS Kubernetes Benchmark](/display/containers/cis+kubernetes+benchmark)**  — The Center for Internet Security (CIS) Kubernetes Benchmark is a reference document that can be used by system administrators, security and audit professionals and other IT roles to establish a secure configuration baseline for Kubernetes. CIS Benchmarks are developed by an open community of security practitioners and licensed under a&nbsp;Creative Commons Attribution-NonCommercial-ShareAlike 4.0 Internal Public License. This page gather&nbsp;resources about&nbsp;CIS Kubernetes benchmark and how to implement i
