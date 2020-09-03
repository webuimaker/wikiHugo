---
# Homepage
title: "Kubernetes Deployment 101"
description: "Get started with Kubernetes deployment: with common Kubernetes deployment tasks and deployment strategies including rolling updates, blue-green, and canary releases."
titleDescription: "Get started with Kubernetes deployment: with common Kubernetes deployment tasks and deployment strategies including rolling updates, blue-green, and canary releases."
type: "widget_page"
url: "/display/containers/kubernetes+deployment+101"  
rightSide: false # true or false for right side bar
# permalink: "/display/containers/container-security-management/"
# headless = true  # Homepage is headless, other widget pages are not.
active: true
breadcrumbs:
 - text: Container Technology Wiki
   url: "/"
 - text: Kubernetes Guide
   url : "/display/containers/Kubernetes+guide"
 - text: Kubernetes 101
   url : "/display/containers/Kubernetes+101"
 - text: Kubernetes Deployment 101
   url : ""
promotion:
  enable: false
  promoLogo: 
  promoBackground: 
  promoHeading:
  promoSubHeading: 
  promoBtnBg:
  promoBtnText: 
  promoBtnUrl: 
bannerTitle: "Kubernetes Deployment 101"
tocBasicAdv:
  enable: true
  title: "In this page: Kubernetes basics"
  tocList:
  - name: "Kubernetes Deployment 101"
    url: "#kubernetes-deployment-101"
  - name: "Key Components of Kubernetes"
    url: "#key-components-of-kubernetes"
  - name: "Common Deployment Tasks"
    url: "#common-deployment-tasks"
  - name: "Deployment Commands"
    url: "#deployment-commands"
  - name: "Deployment Strategies"
    url: "#deployment-strategies"
  - name: "Conclusion"
    url: "#conclusion"
  - name: "Further Reading"
    url: "#further-reading"
    
---
Kubernetes has exploded in growth over the past few years because of its powerful abilities to manage containers in production. While it’s easy to spin up your first container locally, taking containers into production in a cloud environment is a completely different ball game. There are numerous aspects like scale, networking, security, high availability, and performance that need to be considered. All of these factors come into play when deploying containers. This makes deployment the most stressful part of running containers in production. Fortunately, Kubernetes is a mature and robust option for running containers in production and has some strong defaults, wide-ranging options, and is a complete package when looking for a tool to deploy containerized applications.

