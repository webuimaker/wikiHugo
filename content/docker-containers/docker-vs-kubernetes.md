---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 9  # Order that this section will appear.
title: "DOCKER VS. KUBERNETES"
titleColor: 
subtitle: ""
sectionHeadingID: "DockerContainers-DOCKERVS-KUBERNETES"
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"

---

## Comparing Mindshare


Let us take a quick look at how each of these alternatives differs from Docker:

{{< table >}}
<table class="table">
    <thead>
    <tr>
        <th>Mindshare Metric</th>
        <th>Kubernetes</th>
        <th>Docker Swarm</th>
    </tr>
    </thead>
    <tbody>
        <tr>           
            <td><strong>Pages Indexed by Google Past Year</strong></td>
            <td>
                1,190,000
            </td>
            <td>
                135,000
            </td>
        </tr>
        <tr>           
            <td><strong>News Stories Past Year</strong></td>
            <td>
                36,000
            </td>
            <td>
                3,610
            </td>
        </tr>
        <tr>           
            <td><strong>Google Monthly Searches</strong></td>
            <td>
                165,000
            </td>
            <td>
                33,100
            </td>
        </tr>
        <tr>           
            <td><strong>Github Stars</strong></td>
            <td>
                28,988
            </td>
            <td>
                4,863
            </td>
        </tr>
        <tr>           
            <td><strong>Github Commits</strong></td>
            <td>
                58,029
            </td>
            <td>
                3,493
            </td>
        </tr>
    </tbody>
<table>

{{</ table >}}



> These stats are correct as of November, 2017, and will be updated every few months


## Technical Comparisons from the Community

{{< box >}}
### Mesosphere: Docker Engine vs. Kubernetes vs. Mesos

<small>Updated</small>

<small>Opinion by:</small><br>
<small>Amr Abdelrazik, Director, Product Marketing, Mesosphere</small>

---

#### What is covered:

- Detailed architecture overview
- What each solution was intended to solve
- Recommends the right solution for different use cases

---

####  Insight:

Each technology was designed for a different purpose. Docker provided a standard file format for encapsulating applications. Kubernetes helps orchestrate containers at large scale. Mesos is actually not an orchestrator, it is a cluster management platform that can run any workloads, including containers (using the Marathon project). Mesos is agnostic to infrastructure giving it higher portability. 

---

#### Bottom line:

If you are a developer looking for way to build and package applications, Docker is the best solution. For a DevOps team wanting to build a system dedicated exclusively to Docker containers, Kubernetes is the best fit. For organizations running multiple mission critical workloads including Docker containers, legacy applications (e.g., Java), and distributed data services (e.g., Spark, Kafka, Cassandra, Elastic), Mesos is the best fit. 

---

#### Grain of salt:

Mesosphere is the commercial supporter of the Mesos project.
<center>
{{< read-more "Read the full article" "https://mesosphere.com/blog/docker-vs-kubernetes-vs-apache-mesos/" "_blank"  >}}
</center>

{{</ box >}}



{{< box >}}
### Platform9: Kubernetes vs. Docker Swarm


<small><strong>Date:</strong></small> <br> June 22, 2017

<small>Opinion by:</small><br>
<small>Akshai Parthasarathy, Technical Product Marketing Manager, Platform9</small>

---

#### What is covered:

- Detailed architecture overview of both systems
- Feature comparison: Application definition, scalability constructs, high availability, load balancing, auto-scaling for the application, rolling upgrades and rollback, health checks, storage, networking, service discovery, performance and scalability.
  
---

#### Bottom line:

Kubernetes has over 80% of mindshare for news articles, Github popularity, and web searches, and is the default choice for users. However, there is consensus that Kubernetes is more complex to deploy and manage. The Kubernetes community has tried to mitigate this drawback by offering a variety of deployment options, including Minikube and kubeadm.

---

#### Grain of salt:

Platform9 offers a managed Kubernetes service.

<center>
{{< read-more "Read the full article" "https://platform9.com/blog/kubernetes-docker-swarm-compared/" "_blank"  >}}
</center>

{{</ box >}}

## Business Commentaries

{{< box >}}

### Forbes: Docker and Kubernetes, Friends or Foes?

<small><strong>Date:</strong></small> <br> April 28, 2017

<small>Opinion by:</small><br>
<small>Mike Kavis, VP/Principal Architect for Cloud Technology Partners</small>

---

#### The gist:
While industry commentators talk about a battle between Docker and Kubernetes, in reality Docker is a wider platform and not just about containers. The orchestration tier is only one part of Docker's offering, and there is still a very big need for the platform, even if the orchestration layer were replaced with Kubernetes.

---

#### Bottom line:

Kubernetes is an enabler for Docker, not a competitor. Docker's main interest is to have more Docker engines running, which will increase their support revenues. Support for Kubernetes and greater uptake of Kubernetes should only help with this goal.


<center>
{{< read-more "Read the full article" "https://www.forbes.com/sites/mikekavis/2017/04/28/docker-and-kubernetes-friends-or-foes/#6f668a223394" "_blank"  >}}
</center>



{{</ box >}}

{{< box >}}

## The Register: Kubernetes has won. Docker Enterprise Edition will support rival container-wrangling tech

<small><strong>Date:</strong></small> <br> October 17, 2017

<small>Opinion by:</small><br>
<small>Thomas Claburn, Journalist, former editor at InformationWeek</small>

---

#### The gist:

Both Docker and Mesos realized that mindshare behind Kubernetes is just too big and made a pragmatic decision to support Kubernetes, while not giving up on their native solutions, Swarm and Marathon.

---

#### Bottom line:

Docker Swarm and Mesos/Marathon are good solutions, but analysts believe Kubernetes will eventually take over, and there is no room in the market for three orchestration platforms. 


<center>
{{< read-more "Read the full article" "https://www.theregister.co.uk/2017/10/17/docker_ee_kubernetes_support/" "_blank"  >}}
</center>

{{</ box >}}


Read more on this wiki: {{< read-more "Docker vs. Kubernetes - 8 Industry Opinions" "/display/containers/Docker+vs.+Kubernetes+-+8+Industry+Opinions"  >}}



