---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 6  # Order that this section will appear.
title: "6.KUBERNETES DEPLOYMENT"
titleColor: 
subtitle: ""
sectionHeadingID: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---

While it’s easy to spin up your first container locally, taking containers into production in a cloud environment is a completely different ball game. There are numerous aspects like scale, networking, security, high availability, and performance that need to be considered. All of these factors come into play when deploying containers. This makes deployment the most stressful part of running containers in production. Fortunately, Kubernetes is a mature and robust option for running containers in production and has some strong defaults, wide-ranging options, and is a complete package when looking for a tool to deploy containerized applications.

## Deployment Commands

{{< table >}}

| Create a deployment based on a YAML file |
|-----------|
|   kubectl create  |

{{< /table >}}

{{< table >}}

| Deploy using a phased rolling update |
|-----------|
|   kubectl rollout  |

{{< /table >}}

{{< table >}}

| Check the status of a rolling update |
|-----------|
|   kubectl rollout status |

{{< /table >}}

{{< table >}}

| Rollback a recent or ongoing rolling update to a previous version |
|-----------|
|   kubectl rollback  |

{{< /table >}}

{{< table >}}

| Option to delete old replicas |
|-----------|
|   .spec.revisionHistoryLimit  |

{{< /table >}}

## Kubernetes Deployment Strategies

*   **Recreate Deployment** - In this approach all replicas are killed, and are then replaced by new replicas. It involves some downtime for as long as it takes for the system to shut down and boot up again. This works fine for applications that are used infrequently, and where users don’t expect them to be available 24x7\. This is rare in today’s cloud-driven world, and hence, this isn’t the most popular deployment method.

*   **Rolling Update**- when a deployment command is executed, Kubernetes starts to replace existing replicas with the new updated ones one at a time. This scaling up and scaling down of replicas is how Kubernetes manages deployments, and is what makes Kubernetes particularly effective at managing deployments with containers.

*   **Blue-green Deployments** - not native to Kubernetes, but you can set them up with ease. In this method the ‘blue’ replicas are the existing instances, and they are to be replaced by the ‘green’ replicas. Once the green replicas are deployed and tested, you can use an external load balancer to route traffic from the ‘blue’ replicas to the ‘green’ ones. The biggest advantage of blue-green deployments is that it ensures a smooth transition without any downtime.

*   **Canary Releases** - releasing a new version of the app to a subset of users, say 5% of all users. Once this version is tested and reliable for the initial 5% it is released to a bigger subset, until eventually all users get updated to the release without experiencing any downtime. Canary releases let you to test the app in real-world conditions and with real users, however, it does take some upfront planning and management to ensure the release is seamless for the user.


**Learn more about** {{< read-more "Kubernetes Deployment" "/display/containers/kubernetes+deployment+101" >}}


## Kubernetes in Production

The default configurations for Kubernetes components are not designed for heavy and dynamic production workloads, characteristic of DevOps environments and micro-services based application deployments where containers are quickly created and destroyed. Learn how to create a production-ready Kubernetes cluster, including examples and tutorials.

**See our compilation of resources about** {{< read-more "Kubernetes in Production" "/display/containers/kubernetes+in+production" >}}


## Running Kubernetes on AWS

Amazon Web Services (AWS) is a popular cloud provider option for Kubernetes deployments, as it allows unlimited scaling of an enterprise containerized application clusters. AWS’ region availability all around the world means Kubernetes clusters can benefit from very low latencies. Additionally, the wide range of AWS services like S3 for raw storage or RDS for relational databases, it becomes easy to use Kubernetes for both stateless and stateful workloads integrated with native AWS services.

## Running Kubernetes Cluster on AWS Using Kops

Kops is a production grade tool used to install, upgrade, and operate highly available Kubernetes clusters on AWS and other cloud platforms using the command line. Kops is capable of generating Terraform templates with support for multiple [CNI networking](https://kubernetes.io/docs/concepts/cluster-administration/network-plugins/#cni) plugins and custom Kubernetes add-ons.

Note that all kops commands below that include ```--yes``` option can be run first without it to just show which changes would take place (for example, which AWS resources will get created or destroyed when running the command with ```--yes``` option).

The following command will create a 1 master (an ```m3.medium``` instance) and 2 nodes (two ```t2.medium``` instances) cluster in ```us-west-2a``` availability zone:

```java
# kops create cluster \ --name my-cluster.k8s.local \ --zones us-west-2a \ --dns private \ --master-size=m3.medium \ --master-count=1 \ --node-size=t2.medium \ --node-count=2 \ --state s3://my-cluster-state \ --yes
```

## Using the Kubernetes EKS Managed Service

Amazon Elastic Container Service for Kubernetes (EKS) is a fully managed service that takes care of all the cluster setup and creation, ensuring multi-AZ support on all clusters and automatic replacement of unhealthy instances (master or worker nodes). It also patches and upgrades clusters to the latest recommended Kubernetes release without requiring any intervention.

![Using the Kubernetes EKS Managed Service](https://lh3.googleusercontent.com/jcoGFDPX_ThhaErPQmn_CCJgG0NosAprWoyKEikmeFQ2F--afLX1MlsV_p00Wz-UgxIbBVIIABz3RGAJvHevn_5TSpealIjzDz5ScyhzIctW6nJnKLvsswtPf71uJgLnYMEEndWK)

Worker nodes are launched on the AWS user’s own EC2 instances, thus not shared with other tenants. In order to use tools such as ```kubectl``` , access to master instances must be set up via IAM authenticated public endpoints or through [AWS PrivateLink](https://aws.amazon.com/blogs/aws/aws-privatelink-update-vpc-endpoints-for-your-own-applications-services/) . With AWS PrivateLink, masters appear as an elastic network interface with private IP addresses in the Amazon VPC. This allows to the masters and the EKS service directly from the Amazon VPC, without using public IP addresses or requiring the traffic to traverse the internet.

Amazon EKS also integrates tightly with other AWS services such as ELB for load balancing, or [AWS CloudTrail](https://aws.amazon.com/cloudtrail/) for logging.