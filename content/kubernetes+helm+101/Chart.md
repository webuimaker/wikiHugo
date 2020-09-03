---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 8  # Order that this section will appear.
title: "Chart Templates and Values"
titleColor: ""
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
A Chart template is a mechanism by which the creator of the chart can define variables that users can modify when installing the chart. Those variables are called values, and the chart must define reasonable defaults for all values to ensure the chart installs correctly out of the box.

Chart templates are written in Go. All template files are stored in a chart’s `templates/ `folder. When Helm accesses a chart, every file in that directory is rendered via the template engine.

To provide values for a template in a specific chart:

* You can provide a file called `values.yaml` inside of a chart, which contains default values.
* Chart users may supply a YAML file that contains values. This can be provided in the `helm install` command. User-provided values override the default values in the `values.yaml` file.
  
Following is an example of a template file:

```
apiVersion: v1
kind: ReplicationController
metadata:
  name: deis-database
  namespace: deis
  labels:
    heritage: deis
spec:
  replicas: 1
  selector:
    app: deis-database
  template:
    metadata:
      labels:
        app: deis-database
    spec:
      serviceAccount: deis-database
      containers:
        - name: deis-database
          image: {{.Values.imageRegistry}}/postgres:{{.Values.dockerTag}}
          imagePullPolicy: {{.Values.pullPolicy}}
          ports:
            - containerPort: 5432
          env:
            - name: DATABASE_STORAGE
              value: {{default "minio" .Values.storage}}
```
			  
There are several [pre-defined values](https://docs.helm.sh/developing_charts/#chart-dependencies) in Helm templates which cannot be overriden, such as `Release.Name`, `Release.Time` and `Release.Namespace`.

Following is an example of a `values.yaml` file:

`imageRegistry: "quay.io/deis"
dockerTag: "latest"
pullPolicy: "Always"
storage: "s3"`

Values files can specify [global or local values](https://docs.helm.sh/developing_charts/#scope-dependencies-and-values) - indicating whether values should apply only to this chart or to its dependencies as well.
			  
			  
	
**For more details see Helm Documentation:** {{< read-more "Chart Templates and Values" "https://docs.helm.sh/developing_charts/#templates-and-values" "_target"  >}}	
		
		