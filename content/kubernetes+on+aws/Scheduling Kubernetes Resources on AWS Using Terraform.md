---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 5  # Order that this section will appear.
title: "Scheduling Kubernetes Resources on AWS Using Terraform"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
Terraform is an infrastructure-as-code tool used for building, changing, and versioning infrastructure safely and efficiently. It can be used to deploy containerized applications into an properly configured Kubernetes cluster running in AWS.

Terraform uses its own configuration language and by default looks for resource specifications in the same directory where the terraform commands are being executed.

## Specifying Kubernetes as Provider
Terraform needs to be informed of the Kubernetes cluster configuration. For example this Terraform configuration file (extension .tf ):

```
provider "kubernetes" { host = "https://104.196.242.174" username = "my-user" password = "my-password" client_certificate = "${file("~/.kube/client-cert.pem")}" client_key = "${file("~/.kube/client-key.pem")}" cluster_ca_certificate = "${file("~/.kube/cluster-ca-cert.pem")}" }
```

tells Terraform that the Kubernetes master is located at the host IP address and provides the AWS credentials and certificates to ssh to it. We can then install the Terraform plugin for Kubernetes provider by running the command:

`# terraform init`

## Specifying and Deploying Pods and Services
Kubernetes resources like pods and services can be created using Terraform’s configuration language (which then gets translated transparently by Terraform to actual Kubernetes specifications). For example to create a single (nginx) pod and a service selecting this pod:

```
resource "kubernetes_pod" "nginx" { metadata { name = "nginx-example" labels { App = "nginx" } } spec { container { image = "nginx:1.7.8" name = "example" port { container_port = 80 } } } } resource "kubernetes_service" "nginx" { metadata { name = "nginx-example" } spec { selector { App = "${kubernetes_pod.nginx.metadata.0.labels.App}" } port { port = 80 target_port = 80 } type = "LoadBalancer" } }
```

Running the terraform plan command will display the list of actions (resources to destroy, change or create) that Terraform will perform based on the above configuration:

```+ kubernetes_pod.nginx + kubernetes_service.nginx Plan: 2 to add, 0 to change, 0 to destroy.```

Note that the whole configuration of both the pod and service are displayed, but were omitted here for brevity.

Finally, to actually deploy the pod and service, the terraform apply command must be executed. This will create resources via the API in the right order, supplying any defaults as necessary and waiting for resources to finish provisioning to the point when it can either present useful attributes or a failure (with reason) to the user.



	
**For further reading, see Terraform documentation:** {{< read-more "Getting Started with Kubernetes provider" "https://www.terraform.io/docs/providers/kubernetes/guides/getting-started.html" "_target"  >}}	


---