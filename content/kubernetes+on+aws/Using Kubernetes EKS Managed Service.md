---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 3  # Order that this section will appear.
title: "Using Kubernetes EKS Managed Service"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---


Amazon Elastic Container Service for Kubernetes (EKS) is a fully managed service that takes care of all the cluster setup and creation, ensuring multi-AZ support on all clusters and automatic replacement of unhealthy instances (master or worker nodes). It also patches and upgrades clusters to the latest recommended Kubernetes release without requiring any intervention.



While EKS provides similar levels of integration with other Amazon services as ECS, it relies on Kubernetes open orchestration model instead of an AWS specific model. This increases the portability of clusters deployed on EKS to other cloud providers. The key contention for such a migration would be the level of coupling with native AWS services, but at least the orchestration side would be easier.



By default clusters in EKS consist of 3 masters spread across 3 different availability zones to protect against the failure of a single AWS availability zone:

![alt](/images/eks_s1_sushi_donut_1.png)





Worker nodes are launched on the AWS user’s own EC2 instances, thus not shared with other tenants. In order to use tools such as ```kubectl``` , access to master instances must be set up via IAM authenticated public endpoints or through [AWS PrivateLink](href="https://aws.amazon.com/blogs/aws/aws-privatelink-update-vpc-endpoints-for-your-own-applications-services/"). With AWS PrivateLink, masters appear as an elastic network interface with private IP addresses in the Amazon VPC. This allows to the masters and the EKS service directly from the Amazon VPC, without using public IP addresses or requiring the traffic to traverse the internet.



Amazon EKS also integrates tightly with other AWS services such as ELB for load balancing, or [AWS CloudTrail](href="https://aws.amazon.com/cloudtrail/")  for logging.




Standing up a new Kubernetes cluster with EKS can be done simply using the AWS Management Console. After getting access to the cluster, containerized applications can be scheduled in the new cluster in the same fashion as with any other Kubernetes installation:

![alt](/images/eks_main.png)










**For further reading, see AWS documentation:** {{< read-more "Amazon EKS" "https://aws.amazon.com/eks/" "_target"  >}}



---