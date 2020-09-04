---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 4  # Order that this section will appear.
title: "Technical Comparisons from the Community"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---


{{< box >}}
# Mesosphere: Docker Engine vs. Kubernetes vs. Mesos 
<small>

**Undated**

**Opinion by:**

Amr Abdelrazik, Director, Product Marketing, Mesosphere
</small>

---

## What is covered:

- Detailed architecture overview
- What each solution was intended to solve
- Recommends the right solution for different use cases

---

## Insight:

Each technology was designed for a different purpose. Docker provided a standard file format for encapsulating applications. Kubernetes helps orchestrate containers at large scale. Mesos is actually not an orchestrator, it is a cluster management platform that can run any workloads, including containers (using the Marathon project). Mesos is agnostic to infrastructure giving it higher portability. 

---

## Bottom line:
If you are a developer looking for way to build and package applications, Docker is the best solution. For a DevOps team wanting to build a system dedicated exclusively to Docker containers, Kubernetes is the best fit. For organizations running multiple mission critical workloads including Docker containers, legacy applications (e.g., Java), and distributed data services (e.g., Spark, Kafka, Cassandra, Elastic), Mesos is the best fit. 

--- 

## Grain of salt:

Mesosphere is the commercial supporter of the Mesos project.


<center>{{< read-more "Read the full article"  "https://mesosphere.com/blog/docker-vs-kubernetes-vs-apache-mesos/" >}}<center>



{{< /box >}}

{{< box >}}
# Platform9: Kubernetes vs. Docker Swarm
<small>

**Date:**
June 22, 2017
</small>

<small>

**Opinion by:**

Akshai Parthasarathy, Technical Product Marketing Manager, Platform9

</small>

---

## What is covered:


- Detailed architecture overview of both systems
- Feature comparison: Application definition, scalability constructs, high availability, load balancing, auto-scaling for the application, rolling upgrades and rollback, health checks, storage, networking, service discovery, performance and scalability.

---


## Bottom line:
Kubernetes has over 80% of mindshare for news articles, Github popularity, and web searches, and is the default choice for users. However, there is consensus that Kubernetes is more complex to deploy and manage. The Kubernetes community has tried to mitigate this drawback by offering a variety of deployment options, including Minikube and kubeadm.

--- 

## Grain of salt:
Platform9 offers a managed Kubernetes service.




<center>{{< read-more "Read the full article"  "https://platform9.com/blog/kubernetes-docker-swarm-compared/" >}}<center>



{{< /box >}}

{{< box >}}
# Rancher: Docker Swarm vs. Kubernetes White Paper

<small>

**Undated**

**Opinion by:**

Rancher Labs

</small>

---

## What is covered:

- Detailed overview of architecture and usage
- Detailed feature descriptions: networking, storage, scheduling, service discovery, load balancing, scalability, performance
- Comparison table covering installation, ease of use, concepts, best suited for, data volumes, secrets, scaling, and more
- Considerations for application architects - passing credentials, cluster awareness, health checks

---

## Insight:

The two platforms have very different constructs and architecture (nodes/tasks vs. pods), so the choice of orchestrator is not a reversible decision. Apps will have to be architected in a way that is tightly coupled with the orchestrator.    

---

## Bottom line:
IAchieving the same tasks is much more complex in Kubernetes vs. Swarm. But Kubernetes provides a lot of additional functionality like auto-scaling.


--- 

## Grain of salt:

Rancher is a platform for deploying both Kubernetes and Docker Swarm clusters.



<center>{{< read-more "Read the full article"  "http://info.rancher.com/comparing-kubernetes-swarm" >}}<center>

{{< /box >}}

{{< box >}}
# Loom Systems: Kubernetes vs. Docker Swarm vs. Apache Mesos


<small>

**Date**

June 16, 2017

**Opinion by:**

Aviv Lichtigstein, Head of Product Evangelism, Loom Systems


</small>

---

## What is covered:

- Overview of key concepts and components in each system
- Brief feature comparisons across the three systems: cluster installation, container deployment, minimum cluster size, scalability, maturity
- How they compare with orchestration options from public cloud providers

---


## Bottom line:
Docker Swarm is easier to use and more native to Docker, if you don't need bigger scale. Kubernetes is suitable for more complex setups, if you don't need to scale up to thousands of servers. Mesos/Marathon is for big players who need to scale to thousands of servers and/or need to set up scheduling constraints based on host, racks or any other specific variable.



<center>{{< read-more "Read the full article"  "https://www.loomsystems.com/blog/single-post/2017/06/19/kubernetes-vs-docker-swarm-vs-apache-mesos-container-orchestration-comparison" >}}<center>


{{< /box >}}



{{< box >}}
# Stratoscale - Kubernetes vs. Docker Swarm: An Architect's Perspective


<small>

**Undated**

**Opinion by:**

Rotem Dafni, R&D at Stratoscale

</small>

---

## What is covered:

- History of container orchestration
- Feature comparison with code samples: installation and operations, images update, separation of environments, secrets
- Comparison of market interest and popularity
- Availability on public clouds

---
## Bottom line:
From an architect’s perspective, Swarm's advantage is that it is easy to create and deploy cluster for testing purposes. Kubernetes needs a more complex procedure to deploy. But Kubernetes has namespace separation, a great feature that provides one way to use the same cluster for production, staging and development, avoiding the need for test clusters. The market is heavily interested in Kubernetes, so a bigger community is available. 

--- 

## Grain of salt:

Stratoscale's product helps deploy Kubernetes on-prem and on AWS.


<center>{{< read-more "Read the full article"  "https://www.stratoscale.com/blog/kubernetes/kubernetes-vs-swarm-an-architects-perspective/" >}}<center>

{{< /box >}}



{{< box >}}
# Kubernauts.io - Kubernetes vs. Mesos vs. Docker Swarm



<small>

**Date**
June 15, 2017

**Opinion by:**

Arash Kaffamanesh, independent blogger


</small>

---

## What is covered:

- Detailed requirements one should consider before selecting a container orchestrator
- High level summary comparison table
- Research on which Kubernetes versions are actually used in production
- Container as a service options

---
## Bottom line:
Apache Mesos supported by Mesosphere still has a strong place when it comes to big data and data analytics tools like Apache Spark. Docker Swarm is popular, but Kubernetes has the largest momentum as a default tool for managing containers at scale.



<center>{{< read-more "Read the full article"  "https://blog.kubernauts.io/your-container-orchestration-needs-kubernetes-vs-mesos-vs-docker-swarm-1efa9acb69be" >}}<center>

    

{{< /box >}}


