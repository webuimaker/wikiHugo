---
# Homepage
title: "Docker Deployment"
description: "Learn about deploying Docker: microservices architecture, orchestration tools, Service Mesh for networking, security concerns, and more."
titleDescription: "Learn about deploying Docker: microservices architecture, orchestration tools, Service Mesh for networking, security concerns, and more."
type: "widget_page"
url: "/display/containers/docker+deployment"  
rightSide: true # true or false for right side bar
# permalink: "/display/containers/container-security-management/"
# headless = true  # Homepage is headless, other widget pages are not.
active: true
breadcrumbs:
 - text: Container Technology Wiki
   url: "/"
 - text: Docker Containers
   url : "/display/containers/docker+containers"
 - text: Docker 101
   url : "/display/containers/docker+101"
 - text: Docker Deployment
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
bannerTitle: "Docker Deployment"
tocBasicAdv:
  enable: true
  title: "In this page: everything you need to know about deploying Docker."
  tocList:
  - name: "Docker Deployment"
    url: "#docker-deployment"
  - name: "Transition to Microservices"
    url: "#Transition to Microservices"
  - name: "Use an Orchestration Tool"
    url: "#Use an Orchestration Tool"
  - name: "Adopt the Service Mesh"
    url: "#Adopt the Service Mesh"
  - name: "Take an Integrated Approach to Security"
    url: "#Take an Integrated Approach to Security"
  - name: "Additional Resources"
    url: "#Additional Resources"
  - name: "Useful Links"
    url: "#Useful Links"
  - name: "Further Reading"
    url: "#further-reading"
    
---
It’s very easy and quick to get started with [Docker](/display/containers/Docker+vs.+Vagrant) on your laptop. It takes a few minutes to download a container image and spin up a new container from it locally. What starts out so simple gets complicated as you scale to hundreds of containers, and want to deploy these containers into production. All of a sudden you need to think of how to execute all the tasks related to container management, how to transition to a microservices architecture, and how to secure containers in production.


