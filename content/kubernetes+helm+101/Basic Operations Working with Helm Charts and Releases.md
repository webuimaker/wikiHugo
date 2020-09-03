---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 4  # Order that this section will appear.
title: "Basic Operations Working with Helm Charts and Releases"
titleColor: ""
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
To search for available charts, run the command helm search. You can add a search query at the end of the command to filter your search, like this: helm search nginx 

The output looks like this:

`$ helm search
NAME VERSION DESCRIPTION

stable/drupal 0.3.2 One of the most versatile open source content m...

stable/jenkins 0.1.0 A Jenkins Helm chart for Kubernetes.

stable/mariadb 0.5.1 Chart for MariaDB

stable/mysql 0.1.0 Chart for MySQL`

To install a package using Helm, run `helm install` NAME - specifying the name of the chart. Here is an example of output when deploying the MariaDB 0.3.0 Helm chart:

```
$ helm install stable/mariadb
Fetched stable/mariadb-0.3.0 to /Users/mattbutcher/Code/Go/src/k8s.io/helm/mariadb-0.3.0.tgz
happy-panda
Last Deployed: Wed Sep 28 14:02:15 2018
Namespace: default
Status: DEPLOYED
Resources:
==> extensions/Deployment
NAME DESIRED CURRENT UP-TO-DATE AVAILABLE AGE
happy-panda-mariadb 1 0 0 0 1s
==> v1/Secret
NAME TYPE DATA AGE
happy-panda-mariadb Opaque 2 1s
==> v1/Service
NAME CLUSTER-IP EXTERNAL-IP PORT(S) AGE
happy-panda-mariadb 10.0.0.70 <none> 3306/TCP 1s
```


Installing a package creates a release on the Kubernetes cluster. In the above example the release name is `happy-panda`.


You can customize a chart before installing by running `helm inspect values`, seeing the current configuration, and then overriding it during installation, like this:

```
$ echo '{mariadbUser: user0, mariadbDatabase: user0db}' > config.yaml
$ helm install -f config.yaml stable/mariadb
```

This example overrides the MariaDB credentials, but accepts the rest of the defaults for the chart. There are several ways to override configuration data during install, each with its specific format and limitations - [see more details](https://docs.helm.sh/using_helm/#customizing-the-chart-before-installing).

<strong>To keep track of a deployed release's status</strong> or see its configuration, run the command `helm status RELEASE_NAME`

<strong>To upgrade a deployed release</strong> when a new version of the Helm chart is released, use the command helm upgrade RELEASE_NAME. The release is upgraded with the same chart, but a new YAML file.

<strong>To roll back to the previous version</strong> of a release after upgrading, use the command rollback RELEASE_NAME 1 - the number specifies how many versions to roll back. the first revision number is always 1. So if you have only upgraded once, you should select 1. If you upgraded four times, you can specify 3 to roll back to the very first version.

<strong>To list all running release</strong>, use `helm list` - see [options](https://docs.helm.sh/helm/#helm-list).

<strong>To create a new chart</strong>, run the command `helm create NAME`. Helm creates a directory structure like this - let's say the deployed app is mysql:


```
mysql/
 |
 |- .helmignore # patterns to ignore when packaging Helm charts.
 |
 |- Chart.yaml # information about the chart
 |
 |- values.yaml # default values for templates
 |
 |- charts/ # other charts the current chart depends on
 |
 |- templates/ # template files
 ```

 
 
 
We'll explain [dependencies](#KubernetesHelm101-chart-dependencies) and [templates](#KubernetesHelm101-chart-values-) below.

<strong>To fetch a chart</strong> and unpack it in a local directory, useful for inspecting, modifying or repackaging charts, run:

helm fetch [flags] [chart URL | repo/chartname]
There are [several options](https://docs.helm.sh/helm/#helm-create) for verifications to perform on the chart, and how it should be unpacked.

<strong>To download a named release</strong> currently installed on the cluster, run:

helm get [flags] RELEASE_NAME
There are [several options](https://docs.helm.sh/helm/#helm-create), mainly for enabling TLS for the download. It is also possible to get hooks, manifest and values for the release, explained below.

<strong>To delete a release and uninstall it from the Kubernetes cluster</strong>, use `helm delete [flags] RELEASE_NAME`. There are several options, including the ability to perform a dry run and simulate a deletion of the release. The `purge` flag removes the release from the store and makes its name free for later use by other releases.



**Learn more about basic chart operations in the Helm** {{< read-more "Quick Start Guide" "https://docs.helm.sh/using_helm/#quickstart-guide" "_target"  >}}

	

**For a quick reference of all commands see** {{< read-more "Helm Commands Documentation" "https://docs.helm.sh/helm/#helm" "_target"  >}}	