---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 10  # Order that this section will appear.
title: "Summary"
titleColor: ""
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
In this page we introduced Helm - an important new component of Kubernetes that simplifies deployments and get you up and running much more quickly. Helm is a package manager, like Yam or Apt, which lets you package together objects comprising a Kubernetes application and install them with one click. 

We covered important Helm concepts such as charts, releases and repositories, explained Helm's client-server architecture, and provided the basics:

* Working with charts and releases
* Defining dependencies between charts
* Defining templates with default values and overriding default values during installation
* Setting up hooks to intervene at specific points during the release lifecycle
* Working with Helm repositories that allow others to view and consume charts you create

This was only a brief guide - we strongly encourage reading Helm's comprehensive documentation to fully understand how Helm works, and how to create charts that will be truly stable and reusable. In particular, review Helm's [Best Practices](https://docs.helm.sh/chart_best_practices/#the-chart-best-practices-guide) which contains important conventions and practices for creating working charts.