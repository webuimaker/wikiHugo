---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 1  # Order that this section will appear.
title: "Transition to Microservices"
titleColor: ""
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"

---
The switch from Docker as an experiment to Docker in production is largely dependent on your organization’s state. Many startups are cloud-native, and for them, running their apps in Docker in production probably happened from day one. But for most SMBs and enterprises, there’s a need to have backward compatibility to support legacy applications and tools that are still in use and are essential to the organization’s day-to-day activities. In these cases, you can’t just run an entire legacy application in a Docker container. Instead, you need a plan to modernize your architecture over time, and in the process move to containers gradually.

From a monolithic application, your goal is to move to a microservices architecture, which allows you to manage your application as a collection of interrelated services that can be managed and deployed separately from each other. This process of decomposing your application starts with peripheral services that are easy to branch out, then moves to the core parts of the application.