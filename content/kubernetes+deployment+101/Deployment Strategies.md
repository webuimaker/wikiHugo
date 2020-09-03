---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 4  # Order that this section will appear.
title: "Deployment Strategies"
titleColor: ""
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
There are many approaches to deployment in Kubernetes ranging from the simple to the complex.

## Recreate Deployment
In this approach all replicas are killed, and are then replaced by new replicas. It involves some downtime for as long as it takes for the system to shut down and boot up again. This works fine for applications that are used infrequently, and where users don’t expect them to be available 24x7. This is rare in today’s cloud-driven world, and hence, this isn’t the most popular deployment method.

## Rolling Update
By default Kubernetes takes a phased approach to updates. When a deployment command is executed, Kubernetes starts to replace existing replicas with the new updated ones one at a time. This scaling up and scaling down of replicas is how Kubernetes manages deployments, and is what makes Kubernetes particularly effective at managing deployments with containers. As discussed earlier, you can rollback a rolling update even when it’s in progress.

## Blue-green Deployments
Blue green deployments are not native to Kubernetes, but you can set them up with ease. In this method the ‘blue’ replicas are the existing instances, and they are to be replaced by the ‘green’ replicas.

First, You setup Deployments to rollout the green replicas alongside the blue ones. This would take additional resources to run both the old and new deployments, but not for long. Once the green replicas are deployed and tested, you can use an external load balancer to route traffic from the ‘blue’ replicas to the ‘green’ ones. Tools like Linkerd allow for advanced load balancing so you can define how much and which kind of traffic you’d like to route to which replicas. The biggest advantage of blue-green deployments is that it ensures a smooth transition without any downtime.

## Canary Releases
A canary release is when you release a new version of the app to a subset of users, say 5% of all users. Once this version is tested and reliable for the initial 5% it is released to a bigger subset, until eventually all users get updated to the release without experiencing any downtime.

The biggest advantage of canary releases is that they enable you to test the app in real-world conditions and with real users. This brings a big boost in productivity. However, it does take some upfront planning and management along the way to ensure the release is seamless from a user experience point of view.

On the Kubernetes blog, Bitmovin has written about how they implement multi-stage canary deployments. They go into more detail about this type of deployment strategy