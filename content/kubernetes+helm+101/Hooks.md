---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 8  # Order that this section will appear.
title: "Hooks"
titleColor: ""
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
Helm provides a hook mechanism, which allows a developer to intervene at specific points in a release’s life cycle. The available hooks are:

* <strong>pre-install:</strong> after templates are rendered, but before resources created in Kubernetes.

* <strong>post-install:</strong> after all resources are loaded 

* <strong>pre-delete:</strong> on deletion request before any resources are deleted

* <strong>post-delete:</strong> on a deletion request after all of the resources have been deleted

* <strong>pre-upgrade:</strong> on an upgrade request after templates are rendered, before any resources are loaded

* <strong>post-upgrade:</strong> on an upgrade after all resources have been upgraded

* <strong>pre-rollback:</strong> on a rollback after templates are rendered, but before any resources have been rolled back

* <strong>post-rollback:</strong> on a rollback request after all resources have been modified

Technically, hooks are Kubernetes manifest files with special annotations in the `metadata` section. They are template files, so you can use all the regular template features. Here is an example of a job declared to be run on post-install:

```
apiVersion: batch/v1
kind: Job
metadata:
  name: "{{.Release.Name}}"
  labels:
    heritage: {{.Release.Service | quote }}
    release: {{.Release.Name | quote }}
    chart: "{{.Chart.Name}}-{{.Chart.Version}}"
  annotations:
    # This is what defines this resource as a hook. Without this line, the
    # job is considered part of the release.
    "helm.sh/hook": post-install
    "helm.sh/hook-weight": "-5"
    "helm.sh/hook-delete-policy": hook-succeeded
spec:
  template:
    metadata:
      name: "{{.Release.Name}}"
      labels:
        heritage: {{.Release.Service | quote }}
        release: {{.Release.Name | quote }}
        chart: "{{.Chart.Name}}-{{.Chart.Version}}"
    spec:
      restartPolicy: Never
      containers:
      - name: post-install-job
        image: "alpine:3.3"
        command: ["/bin/sleep","{{default "10" .Values.sleepyTime}}"]
```
		
Hooks are [managed separately from releases](https://docs.helm.sh/developing_charts/#hook-resources-are-not-managed-with-corresponding-releases) so you should be aware that deleting a release may not delete its associated hooks.
	
**For more details see Helm Documentation:** {{< read-more "Hooks" "https://docs.helm.sh/developing_charts/#hooks" "_target"  >}}	
		
		