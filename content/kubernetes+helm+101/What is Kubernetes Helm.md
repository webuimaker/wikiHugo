---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 1  # Order that this section will appear.
title: "What is Kubernetes Helm"
titleColor: ""
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"

---

Kubernetes Helm is a package manager for Kubernetes, analogous to Yum or Apt. It makes it possible to organize Kubernetes objects in a packaged application that anyone can download and install in one click, or configure to their specific needs. In Helm, these packages are called charts (similar to debs or rpms).

When a user installs a Helm chart, Helm deploys a Kubernetes cluster in the background, as specified in the chart’s configuration.

Helm is organized around several key concepts:

* A <strong>chart</strong> is a package of pre-configured Kubernetes resources
* A <strong>release</strong> is a specific instance of a chart which has been deployed to the cluster using Helm
* A <strong>repository</strong> is a group of published charts which can be made available to others

Kubernetes Helm was developed by Google and Deis and introduced as part of the Kubernetes 1.4 release in 2016\. Because Helm is relatively new, there are few public repositories for Helm packages - one public repo is [hub.kubeapps.com](http://hub.kubeapps.com). Publicly available, stable Helm charts include:

{{< table >}}

<table>
    <tr>
        <td>MySQL</td>
        <td>Redis</td>
        <td>Apache Hadoop </td>
    </tr>
    <tr>
        <td>PostgreSQL</td>
        <td>Drupal</td>
        <td>Apache Spark </td>
    </tr>
    <tr>
        <td>MariaDB</td>
        <td>WordPress</td>
        <td>Apache Kafka </td>
    </tr>
    <tr>
        <td>Redis</td>
        <td>Etcd</td>
        <td>Jenkins</td>
    </tr>
</table>

{{< /table >}}


	  	

	  	

	    	

	  	