---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 2  # Order that this section will appear.
title: "2.HOW DOES KUBERNETES COMPARE TO DOCKER SWARM?"
titleColor: ""
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"

---
[Docker vs. Kubernetes](/display/containers/Docker+vs.+Kubernetes+-+8+Industry+Opinions) - which should you use for container orchestration? Docker Swarm is considered the "lightweight" [alternative to Kubernetes](/display/containers/Kubernetes+Alternatives). Docker swarm mode allows you to manage a cluster of Docker Engines, natively within the Docker platform. You can use the Docker CLI to create a swarm, deploy application services to a swarm, and manage swarm behavior.  


Swarm's capabilities include coordination between containers, allocating tasks to groups of containers, health checks and lifecycle management of containers, redundancy and failover, scaling containers up and down based on load, and rolling updates.

## Comparing Mindshare: Docker vs. Kubernetes

{{< table >}}

| Mindshare Metric | Kubernetes     |  Docker Swarm |
|--------|--------------|---|
|   Google Monthly Searches	  | 165,000 | 33,100  |
|   Pages Indexed by Google Past Year	 |       1,190,000	 |  135,000 |
|     News Stories Past Year	   |    36,000          | 3,610  |
|    Github Stars	    |       28,988       |  4,863 |
|    Github Commits		    |  58,029            |  3,493 |

{{< /table >}}

{{% table %}} table 2 {{% /table %}}

> These stats are correct as of November, 2017, and will be updated every few months

## Technical Comparisons from the Community


{{< box >}}

# Mesosphere: Docker Engine vs. Kubernetes vs. Mesos


Undated

Opinion by: <br> 

Amr Abdelrazik, Director, Product Marketing, Mesosphere

---

##### Insight:

Each technology was designed for a different purpose. Docker provided a standard file format for encapsulating applications. Kubernetes helps orchestrate containers at large scale. Mesos is actually not an orchestrator, it is a cluster management platform that can run any workloads, including containers (using the Marathon project). Mesos is agnostic to infrastructure giving it higher portability. 

---


##### Bottom line:

If you are a developer looking for way to build and package applications, Docker is the best solution. For a DevOps team wanting to build a system dedicated exclusively to Docker containers, Kubernetes is the best fit. For organizations running multiple mission critical workloads including Docker containers, legacy applications (e.g., Java), and distributed data services (e.g., Spark, Kafka, Cassandra, Elastic), Mesos is the best fit. 


[Read the full article]([https://link](https://mesosphere.com/blog/docker-vs-kubernetes-vs-apache-mesos/))

{{< /box >}}

{{< box >}}

# Platform9: Kubernetes vs. Docker Swarm

Date:
June 22, 2017

Opinion by: 

Akshai Parthasarathy, Technical Product Marketing Manager, Platform9


##### Bottom line:

Kubernetes has over 80% of mindshare for news articles, Github popularity, and web searches, and is the default choice for users. However, there is consensus that Kubernetes is more complex to deploy and manage. The Kubernetes community has tried to mitigate this drawback by offering a variety of deployment options, including Minikube and kubeadm.

[Read the full article]([href="https://platform9.com/blog/kubernetes-docker-swarm-compared/")
 
{{< /box >}}

{{< box >}}

# Rancher: Docker Swarm vs. Kubernetes White Paper

Undated

Opinion By: 

Rancher Labs

---

##### Insight: 

The two platforms have very different constructs and architecture (nodes/tasks vs. pods), so the choice of orchestrator is not a reversible decision. Apps will have to be architected in a way that is tightly coupled with the orchestrator.

---

##### Bottom line:

Achieving the same tasks is much more complex in Kubernetes vs. Swarm. But Kubernetes provides a lot of additional functionality like auto-scaling.

[Read the full article]([href="https://platform9.com/blog/kubernetes-docker-swarm-compared/")


{{< /box >}}

**Read more industry opinions on** {{< read-more "Kubernetes vs. Docker" "/display/containers/docker+vs.+kubernetes+-+8+industry+opinions"  >}}


