---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 1  # Order that this section will appear.
title: "Orchestration"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"

---

<strong> What is container orchestration?</strong>

[Container orchestration](/display/containers/Kubernetes+Alternatives) is a way of managing containers at large scale so that they are scalable, automated, secure, and production-ready. Container orchestrators act as a layer of abstraction between the containers and the infrastructure that powers them.

[Docker](/display/containers/Docker+vs.+Vagrant) is the standard container runtime, and you can easily spin up a container locally on your laptop using the Docker CLI. However, to run Docker containers at scale, you need a container orchestrator. This is a management layer for Docker containers and is essential to run containers in production.

## Kubernetes

This is the most popular container orchestrator today and is supported by almost every container vendor. It organizes containers into a collection of pods and has powerful features for deployment, load balancing, security, and more.


**Get started with** {{< read-more "Kubernetes"  "https://kubernetes.io/" "_blank"  >}}

## Swarm

Docker’s default orchestration tool, [Swarm](/display/containers/Docker+Swarm+101), is simpler to use than Kubernetes and is well integrated into the Docker workflow. With the rising popularity of Kubernetes, Swarm has now added support for Kubernetes, and has conceded the orchestration throne to Kubernetes.


**Get started with** {{< read-more "Swarm"  "https://docs.docker.com/engine/swarm/swarm-tutorial/" "_blank"  >}}

## Mesos


Mesos has its own container orchestration tool called Marathon. With the dominance of Kubernetes, Marathon is taking a back seat as its parent company, Mesosphere, shifts focus to give users the choice of Kubernetes.

**Get started with** {{< read-more "Mesos"  "https://open.mesosphere.com/advanced-course/" "_blank"  >}}



**For a deeper comparison of the orchestration tools, go to our** {{< read-more "Swarm 101"  "https://www.aquasec.com/wiki/display/containers/Docker+Swarm+101" "_blank"  >}}page.


CaaS services



<strong>What is a CaaS service?</strong>


A container-as-a-service (CaaS) is a container management tool that is used to control the operation of containers end-to-end. The most popular CaaS tools are provided by the top cloud vendors like AWS, but there are many other smaller CaaS solutions available today that focus on managing container using Kubernetes.


## ECS

Coming from the AWS Stable, [Amazon Elastic Container Service](/display/containers/Amazon+Elastic+Container+Service) is one of the early container services. It has been slow to adopt Kubernetes, but has finally jumped on the Kubernetes bandwagon this past year. It runs containers inside EC2 instances and has deep integration with the wider AWS platform. It’s been the most recent vendor to embrace Kubernetes support, announcing their EKS service for Kubernetes management.

**Get started with** {{< read-more "ECS"  "https://aws.amazon.com/ecs/getting-started/" "_blank"  >}}

## GKE

Google Container Engine (GKE), the container service from Google Cloud is the most deeply integrated with Kubernetes among the CaaS platforms. It is the first to bring upstream Kubernetes releases into its platform and is a great choice if Kubernetes is your priority.


**Get started with** {{< read-more "GKS"  "/display/containers/Google+Container+Engine" "_blank"  >}}

## AKE

Azure Container Engine (AKE), Microsoft’s container service has deep integration with the Azure platform and is taking significant steps to be the best place to manage Kubernetes. It has hired Brendan Burns, Kubernetes' co-founder to help with this mission.

**Get started with** {{< read-more "AKE"  "https://docs.microsoft.com/en-us/azure/aks/intro-kubernetes" "_blank"  >}}

## Other CaaS Services

There are numerous other CaaS platforms with a focus on simplifying Kubernetes management. Some of them are Pivotal Container Service (PKS), Platform9, Heptio, Kismatic, StackPoint, and Giant Swarm, to name a few.



