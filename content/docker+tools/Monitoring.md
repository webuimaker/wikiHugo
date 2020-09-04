---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 4  # Order that this section will appear.
title: "Monitoring"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
Keeping track of changes and events as they occur is an important part of running containers in production. Fortunately, the Docker ecosystem has a range of monitoring tools to choose from.

## Prometheus

Prometheus is by far the most popular monitoring tool for Kubernetes. It focuses on capturing and analyzing time-series data in real-time. It can be integrated with other tools like Kibana for visualization.


**Get started with** {{< read-more "Prometheus"  "https://prometheus.io/" "_blank"  >}}

## Pagerduty

A vendor tool, Pagerduty has become essential to many DevOps teams that want to be alerted in real-time of downtimes, errors, attacks, and more. Its mature routing system ensures the right people are informed of anything going wrong with the system as soon as it happens.


**Get started with** {{< read-more "Pagerduty"  "https://www.pagerduty.com/features/" "_blank"  >}}

## Datadog

Datadog is a container runtime monitoring tool that focuses on live reporting of performance data. It can identify parts of a Kubernetes stack automatically and, with its powerful visualizations, makes monitoring Kubernetes simple.



**Get started with** {{< read-more "Datadog"  "https://www.datadoghq.com/blog/monitoring-kubernetes-with-datadog" "_blank"  >}}

## Slack

Slack enables integration with other tools and streams events to a live chat stream for the entire team to view. It makes troubleshooting and collaboration among team members faster and simpler.


**Get started with** {{< read-more "Slack"  "https://slack.com/get-started" "_blank"  >}}