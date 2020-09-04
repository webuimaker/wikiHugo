---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 1  # Order that this section will appear.
title: "Managing Docker in the Cloud - What Matters"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"

---
When running Dockerized applications in production, the criteria stay the same, but how they play out in production is what differs with containers. Let’s look at a few of these criteria and what changes with them.

## Scale

The first reason most users shift to Docker containers is to take advantage of the scalability it brings. As your app reaches millions of users, VMs are tardy and slow to respond to spikes in traffic, and hyper-growth. By contrast, containers can easily be scaled out or scaled back to meet changing demands.

When running Docker containers in the cloud, you want to be able to run thousands, or hundreds of thousands of containers seamlessly. This is easier said than done. Though Docker enables scale, and it makes managing infrastructure easier at scale, it brings a different type of complexity.

## High availability

Containers are ephemeral in nature and support dynamic workloads. With the constant creation and destruction of containers, you need to ensure high availability for the applications and services they support. Additionally, performance lags should be handled with container-centric load balancing.

Load balancing between containers in the cloud is similar to traditional load balancing, where the workload is shared across multiple instances. Only in this case, the pace of load balancing is much more frantic considering the dynamic nature of containers. The load balancer needs to be aware of the health of containers across all regions and route requests to the instances that are most likely to process the task fastest. AWS ELB is a great example of a load balancer that has evolved to support container workloads.

## Portability

Vendor lock-in is a concern especially for enterprises moving to the cloud. With the complex backend systems and long-running applications, they have a lot to lose by switching infrastructure. At the same time, as they adopt containers, they want to enjoy the benefit of portability that containers promise. While containers bring portability within the development pipeline, portability between cloud providers is yet to become a reality.

As you configure cloud infrastructure to run Docker containers, you want to have the flexibility to switch between cloud providers. But this is easier said than done due to the unique characteristics of each cloud provider. When you choose a cloud vendor’s container service, it follows that you also adopt their unique take on tools for identity and access management (IAM), security, networking, and storage. Moving the container to a different cloud vendor would mean a change to all these aspects of running Docker in the cloud.

While there are obstacles to cloud portability, it’s easier to move between clouds than between hardware servers. Your application code, its binaries and libraries are still isolated from the infrastructure and can be ported over to the other cloud vendor as is. This is a big advantage when running Docker in the cloud. With the recent adoption of Kubernetes as the standard for cloud-based container deployments (Amazon’s EKS, Azure’s AKS and Google’s more mature GKE) some of the differences between container cloud deployments have diminished, showing a trend of improving cross-cloud portability.

## Hosting providers

Perhaps the most important decision when running Docker in the cloud is where to host them. There are numerous options to choose from and the number keeps growing. If you’re already committed to a cloud vendor you need to consider how your operations and costs will change with the move to containers. If you run a hybrid setup of both a private datacenter and public cloud infrastructure you need to think of how to manage containers across both platforms.

There are numerous vendors providing container management services, popularly known as container as-a-service (CaaS). Let’s look at each option and assess how they stack up with the others.