---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 3  # Order that this section will appear.
title: "Deploying Kubernetes on AWS Using Kops"
titleColor: ""
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---



Kops is a production grade tool used to install, upgrade, and operate highly available Kubernetes clusters on AWS and other cloud platforms using the command line. Kops is capable of generating Terraform templates with support for multiple [CNI networking](https://kubernetes.io/docs/concepts/cluster-administration/network-plugins/#cni) plugins and custom Kubernetes add-ons.

## Installing a Kubernetes Cluster on AWS
Before proceeding, make sure to have installed [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/) , [kops]() , and [AWS cli]() tools.



Configure AWS Client with Access Credentials
Make sure AWS IAM user has the following permissions for kops to function properly:

- AmazonEC2FullAccess
- AmazonRoute53FullAccess
- AmazonS3FullAccess
- IAMFullAccess
- AmazonVPCFullAccess

Configure AWS cli with this user’s credentials by running:

```
aws configure
```


### Create S3 Bucket for Cluster State Storage

Create a dedicated S3 bucket which will be used by kops to store the state representing the cluster. We’ll name this bucket my-cluster-state :

```
aws s3api create-bucket --bucket my-cluster-state
```

Make sure to activate bucket versioning to be able to later recover or revert to a previous state:

```
aws s3api put-bucket-versioning --bucket my-cluster-state --versioning-configuration Status=Enabled
```


### DNS Setup

On the DNS side, you can go with either public or private DNS. For public DNS, a valid top-level domain or subdomain is required to create the cluster. DNS is required by worker nodes to discover the master and by the master to discover all the etcd servers. For a domain whose registrar is not AWS, create a [Route 53 hosted zone](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/CreatingHostedZone.html) on AWS and change nameserver records on your registrar accordingly.

In this example we’ll be using a simple, [private DNS to create a gossip-based cluster](http://github.com/kubernetes/kops/blob/master/docs/aws.md#configure-dns) . The only requirement to set this up is for our cluster name to end with k8s.local .



### Creating the Kubernetes Cluster

Note that all kops commands below that include ```--yes``` option can be run first without it to just show which changes would take place (for example, which AWS resources will get created or destroyed when running the command with `--yes` option).

The following command will create a 1 master (an ```m3.medium``` instance) and 2 nodes (two ```t2.medium``` instances) cluster in ```us-west-2a``` availability zone:

 ```#kops create cluster \ --name my-cluster.k8s.local \ --zones us-west-2a \ --dns private \ --master-size=m3.medium \ --master-count=1 \ --node-size=t2.medium \ --node-count=2 \ --state s3://my-cluster-state \ --yes``
 
Some of the command options in the above example have default values: `--master-size` , `--master-count` , `--node-size` , and `--node-count` . We’ve used the default values so the end result would be the same if we hadn’t specified those options. Also note that kops will create one master node in each availability zone specified, so this option: `--zones us-west-2a`,us-west-2b would result in 2 master nodes, one in each of the two zones (even if `--master-count` was not specified in the command line).

Note that cluster creation may take a while as instances must boot, download the standard Kubernetes components and reach a "ready" state. Kops provides a command to check the state of the cluster and check it’s ready:

```
#kops validate cluster --state=s3://my-cluster-state Using cluster from kubectl context: my-cluster.k8s.local Validating cluster my-cluster.k8s.local INSTANCE GROUPS NAME ROLE MACHINETYPE MIN MAX SUBNETS master-us-west-2a Master m3.medium 1 1 us-west-2a nodes Node t2.medium 2 2 us-west-2a NODE STATUS NAME ROLE READY ip-172-20-32-203.us-west-2.compute.internal node True ip-172-20-36-109.us-west-2.compute.internal node True ip-172-20-61-137.us-west-2.compute.internal master True Your cluster my-cluster.k8s.local is ready
```

If you want to make some changes to the cluster, do so by running:

 `kops edit cluster my-cluster.k8s.local # kops update cluster my-cluster.k8s.local --yes`




### Upgrading the Cluster to a Later Kubernetes Release

Kops can upgrade an existing cluster (master and nodes) to the latest recommended release of Kubernetes without having to specify the exact version. Kops supports rolling cluster upgrades where the master and worker nodes are upgraded one by one.

1. Update Kubernetes
   
   ```kops upgrade cluster \ --name $NAME \ --state s3://my-cluster-state \ --yes``` 
2. Update the state store to match the cluster state.
    
    ```kops update cluster \ --name my-cluster.k8s.local \ --state s3://my-cluster-state \ --yes```
3. Perform the rolling update.
   
   ```kops rolling-update cluster \ --name my-cluster.k8s.local \ --state s3://my-cluster-state \ --yes```

This will perform updates on all instances in the cluster, first master and then workers.



### Delete the Cluster

To destroy an existing cluster that we used for experimenting or trials for example, we can run:

```kops delete cluster my-cluster.k8s.local \ --state=s3://my-cluster-state \ --yes```


	
**For further reading, see AWS Documentation:** {{< read-more "Manage Kubernetes Clusters on AWS Using Kops" "https://aws.amazon.com/blogs/compute/kubernetes-clusters-aws-kops/" "_target"  >}}