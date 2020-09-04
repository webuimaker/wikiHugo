---
# Homepage
title: "Docker in Production"
description: "Learn about running Docker in a production environment: strategies for scaling up, selecting a cloud-host vendor, orchestrating multiple clusters of containers, and more."
titleDescription: "Learn about running Docker in a production environment: strategies for scaling up, selecting a cloud-host vendor, orchestrating multiple clusters of containers, and more."
type: "widget_page"
url: "/display/containers/docker+in+production"  
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
 - text: Docker in Production
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
bannerTitle: "Running Docker in Production"
tocBasicAdv:
  enable: true
  title: "In this page: everything you need to know about running Docker in production."
  tocList:
  - name: "Running Docker in Production"
    url: "#running-docker-in-production"
  - name: "Start Small"
    url: "#Start Small"
  - name: "Decide Where To Run It"
    url: "#Decide Where To Run It"
  - name: "Orchestration is a Necessity"
    url: "#Orchestration is a Necessity"
  - name: "Make Your Docker Images Private"
    url: "#Make Your Docker Images Private"
  - name: "Monitor and Log Everything"
    url: "#Monitor and Log Everything"
  - name: "Further Reading"
    url: "#further-reading"
    
---
Running [Docker](https://www.aquasec.com/wiki/display/containers/Docker+Containers) in production doesn't necessarily mean less work than running VMs in production. Your containers won’t magically run on their own. In fact, Docker in production may mean more work than managing VMs. However, it’s the only way forward if you want to modernize your applications and deliver a user experience that your customers expect. Docker does this by adding speed to every step of the development pipeline. It makes every step - development, testing, and deployment - repeatable, automated and highly programmatic.


