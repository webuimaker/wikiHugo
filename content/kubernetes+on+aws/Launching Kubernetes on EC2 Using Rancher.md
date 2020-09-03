---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 4  # Order that this section will appear.
title: "Launching Kubernetes on EC2 Using Rancher"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
[Rancher](https://rancher.com/) is a complete container management platform that eases deployment of Kubernetes and containers. Rancher natively supports Kubernetes and allows users to control its features through a simple UI, including updates to the latest stable release. It integrates with LDAP, AD, and GitHub for authentication. Rancher also provides an [application catalog with over 90 popular Docker applications](http://rancher.com/catalog-items/) .

## Setting Up Rancher in AWS

Rancher (the application) runs on RancherOS, which is available as an Amazon Machine Image (AMI), and thus can be deployed on any EC2 instance.

<strong>Create RancherOS Instance on EC2</strong>


After installing and configuring AWS CLI tool, proceed to create an EC2 instance using RancherOS AMI. Check RancherOS documentation for AMI ids for each region. For example this command:



`$ aws ec2 run-instances --image-id ami-12db887d --count 1 --instance-type t2.micro --key-name my-key-pair --security-groups my-sg`

will create one new t2.micro EC2 instance with RancherOS on ap-south-1 AWS region. Make sure to use the correct key name and security group. Also make sure the security group enables traffic to TCP port 8080 to the new instance.

<strong>Start Rancher Server</strong>

When the new instance is ready, just connect using ssh and start the Rancher server:



`$ sudo docker  run  --name rancher-server -d --restart=unless-stopped \ `
  `-p 8080:8080 rancher/server:stable`
  
This might take a few minutes. Once done, the UI can be accessed on port 8080 of the EC2 instance . Since by default anyone can access Rancher’s UI and API, it is recommended to set up [access control](http://rancher.com/docs/rancher/latest/en/configuration/access-control/).




## Creating a Kubernetes cluster via Rancher in AWS


<strong>Configure Kubernetes environment template</strong>

An environment in Rancher is a logical entity for sharing deployments and resources with different sets of users. Environments are created from templates. Rancher’s application catalogue already includes templates for Kubernetes that can be selected and modified to configure, among other: [disabling add-ons](http://rancher.com/docs/rancher/latest/en/kubernetes/addons/) (Rancher installs by default: [Helm](http://rancher.com/docs/rancher/latest/en/kubernetes/addons/#helm) , Dashboard and [SkyDNS](http://rancher.com/docs/rancher/latest/en/kubernetes/addons/#skydns) ), [enabling backups](http://rancher.com/docs/rancher/latest/en/kubernetes/backups/) , and selecting the [cloud provider](http://rancher.com/docs/rancher/latest/en/kubernetes/providers/) for managing load balancers, nodes and networking routes.



<strong>Create the Kubernetes Cluster (environment)</strong>

Adding a Kubernetes environment is just a matter of selecting the adequately configured template for our use case and inputting the cluster name. If access control is turned on, we can add members and select their membership role . Anyone added to the membership list would have access to the environment.



<strong>Add Hosts to Kubernetes Cluster</strong>

We need to add at least one host to the newly created Kubernetes environment. In this case, the hosts will be previously created AWS EC2 instances.

Once the first host has been added, Rancher will automatically start the deployment of the infrastructure (master) including Kubernetes services (i.e. kubelet, etcd, kube-proxy, etc). Hosts that will be used as Kubernetes nodes will require TCP ports 10250 and 10255 to be open for kubectl. Make sure to review the full list of Rancher requirements for the hosts .

It might take a few minutes for the Kubernetes cluster setup/update to complete, after adding hosts to Kubernetes environment:





## Deploying Applications in the Kubernetes Cluster

Once the cluster is ready containerized applications can be deployed using either the Rancher application catalog or kubectl. kubectl needs to be configured via the Rancher UI in order for deployment information to become visible in Rancher’s dashboards.

**For further reading, see Rancher documentation:** {{< read-more "Kubernetes" "http://rancher.com/docs/rancher/latest/en/kubernetes/" "_target"  >}}	