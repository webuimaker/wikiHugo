---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 2  # Order that this section will appear.
title: "Common Deployment Tasks"
titleColor: ""
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---






## Execute a Deployment
To initiate a deployment you need to create a YAML file with the specifications for the deployment using the kubectl create command.

## Rollback During a Deployment
Kubernetes always records the change history for deployments in the pod template file. If a deployment has issues and you want to revert to an older version while a deployment is in progress you need to run the rollback command which will stop the existing deployment and start reverting back to the old replicas. This is possible because of the way Kubernetes scales replicas up and down during a deployment.

If you’ve labeled your previous deployments, you can even rollback to a specific previous deployment.

Kubernetes also lets you pause a rollout, update any images that are part of that deployment, and then resume the rollout. This way you can reduce the number of rollouts.

## Phases of a Deployment
Kubernetes has multiple phases for a deployment. A deployment can be in progress, complete, or failed. You can view the state of a deployment by running the kubectl rollout status command.

A deployment can fail due to many reasons such as resource constraints, image pull errors, inadequate permissions and more.

## Clean-up After a Deployment
After every deployment Kubernetes automatically checks for previous replicas that can be deleted. You specify how many past versions you’d like to keep using the .spec.revisionHistoryLimit field. The default value is 2, and if you set it to 0 all older replicas will be deleted. But ideally, you want to keep some of the older replicas in case you’d like to rollback any deployment.






