---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 3  # Order that this section will appear.
title: "Azure Container Service (AKS)"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---


{{< table >}}
<table>
<tr>
<th>What is AKS?
</th>
</tr>
<tr>
<td><p> Microsoft Azure is one cloud vendor that has made giant strides to adopt Kubernetes quickly. With its recent platform-wide upgrade and rebranding to <a href="https://docs.microsoft.com/en-us/azure/aks/"   target="_blank"> AKS</span></a> , Azure now makes it easy to run Kubernetes clusters without requiring prior experience in managing Kubernetes. </p>
</td>
</tr>
</table>

{{< /table >}}


AKS particularly focuses on making it easy to get started in as quick as 5 minutes, and thereafter, making it easy to install new upgrades and patches, and simplifying scaling of clusters.

Azure still supports other orchestrators on AKS, so if you want to use Mesos or Swarm or Nomad, you can. Kubernetes is the most preferred way of running Docker containers in the cloud, and in this sense, Azure is on the right track in focusing on Kubernetes.

Azure also offers [Azure Container Instances](https://azure.microsoft.com/en-us/services/container-instances/) that makes it extremely easy to get up and running with containers in the cloud. ACI doesn’t have a graphical interface, as of yet. It works only via the Azure CLI, and lets you spin up a container instance with a single command. It’s in preview stage and isn’t very well integrated with the rest of the Azure Cloud platform. However, its strength lies in its simplicity. It’s meant to be the fastest way to get up and running without having to configure any VMs, or deal with container tools. All you need is your application code and you can package it in a container and push it into production with just a single command. While the service is not yet ready for prime time, it’s surprisingly simple to get started with, and is especially great for those who are just getting started running Docker in the cloud.






**Get started with** {{< read-more "AKS"  "https://docs.microsoft.com/en-us/azure/aks/" "_blank"  >}}

