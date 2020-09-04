---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 2  # Order that this section will appear.
title: "Docker Cloud"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---

{{< table >}}
<table>
<tr>
<th>What is Docker Cloud?
</th>
</tr>
<tr>
<td>
Docker Cloud is Docker’s own container hosting service. It provides a private registry, and a way to set up automated builds and tests for container images.
</td>
</tr>
</table>

{{< /table >}}


For deployment, Docker Cloud leverages Docker Swarm and can deploy containers on its own Docker Cloud platform or any public cloud platform. While this is a good option for a developer environment, for production workloads many organizations find themselves committed to a public cloud vendor like AWS where they host much of their other infrastructure. In this case, a CaaS service from one of the public cloud vendors is an attractive option to host Docker containers.



**Get started with** {{< read-more "Docker Cloud"  "https://cloud.docker.com/" "_blank"  >}}



## [AWS ECS]()


{{< table >}}
<table>
<tr>
<th>What is AWS?
</th>
</tr>
<tr>
<td><p><a href="https://docs.microsoft.com/en-us/azure/aks/"  target="_blank">AWS</a> is the largest cloud vendor,  and its  <a href="https://aws.amazon.com/ecs/"   target="_blank">EC2 container service</a> (ECS) is a natural fit for any organization that already runs  predominantly  on AWS. </p>
</td>
</tr>
</table>

{{< /table >}}



With cloud vendors, the norm is to run your containers within VMs. In the case of AWS, this means running containers within EC2 instances.

The biggest benefit of going with a cloud vendor like AWS is that the container service is deeply integrated with their cloud platform. This means you can easily leverage services like IAM for access management, S3 for storage, and CloudTrail for API logging.

AWS has recently announced full support for Kubernetes as it adopts the now-industry-standard for container orchestration. Its new [Elastic Kubernetes Service](https://aws.amazon.com/eks/) (EKS) service makes it easy to run Kubernetes in production by simplifying setup and management of Kubernetes clusters. Once an app is deployed on EKS, AWS handles automatic scaling and high availability. EKS constantly monitors masters and automatically replaces unhealthy ones.

To bring up the advantage of portability, AWS touts that EKS can handle any existing Kubernetes workload whether on-premise or in any other public cloud. They promise easy migration to EKS promising that your EKS Kubernetes clusters will be fully compatible with Kubernetes community tooling such as Kubectl.

Related to EKS, AWS also announced a very interesting add-on to its ECS service called [Fargate](https://aws.amazon.com/blogs/aws/aws-fargate/). It’s a bit like AWS Lambda for containers. Fargate’s biggest strength is that it completely abstracts away the underlying infrastructure leaving you to focus on your containers and applications instead. You still have control over what goes in your containers, who has access to them, how they’re networked, and how they handle workloads. But the drudge of configuring the perfect infrastructure to power all this is no longer required. You can just define the required CPU and memory and Fargate ensures you always have those resources available for your containers.




**Get started with** {{< read-more "AWS"  "https://docs.microsoft.com/en-us/azure/aks/" "_blank"  >}}
