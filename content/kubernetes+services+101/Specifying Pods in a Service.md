---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 3  # Order that this section will appear.
title: "Specifying Pods in a Service"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---



A service in Kubernetes can be created via an API request by passing in a service definition such as:


```
kind: Service
apiVersion: v1
metadata:
  name: my-service
spec:
  selector:
    app: MyApp
  ports:
    - protocol: TCP
      port: 80
      targetPort: 9376
```
   
In this example the new service is named `my-service` and will target TCP port 9376 on any pod with the metadata label `"app=MyApp"` . Kubernetes constantly evaluates the service’s label selector to determine at any given moment which pods are included in the service. This means that a new service can include existing pods that already match the label selector.

To facilitate port changes in the pods/applications, Kubernetes supports strings for `targetPorts`, so each pod in the service can expose a different port, as long as there’s a mapping to a commonly named port. This allows, for example, to change the port number that pods expose in the next version of your backend software, without breaking clients.




**For further reading, see Kubernetes Documentation:** {{< read-more "Defining a service" "https://kubernetes.io/docs/concepts/services-networking/service/#defining-a-service" "_target"  >}}