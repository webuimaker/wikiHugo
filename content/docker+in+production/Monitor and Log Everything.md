---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 5  # Order that this section will appear.
title: "Monitor and Log Everything"
titleColor: ""
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
You can only manage what you monitor. In production, visibility is key to running a successful Docker operation. When running distributed Docker systems that span hundreds or thousands of container instances, tracking the performance of all these instances can be a daunting task. The reporting data needs to real-time, easy to correlate, and have enough detail for you to drill down into the root cause of issues.

For a Docker stack, especially one powered by Kubernetes, [Prometheus](https://prometheus.io/) has emerged as the leading monitoring tool. Its uniqueness is that it monitors only time-series metrics, and lets you easily correlate one metric with another at the same point in time. It works well with Kubernetes able to automatically identify components like pods, containers, nodes, and services. Prometheus is easily integrated with Kibana for advanced visualization and quicker analysis of monitoring data.

> Running Docker in production is full of challenges at every step. But by taking the right approach you can save yourself a lot of mistakes, and ease your transition to the other side - the place where Docker has transformed the way you build and ship applications.