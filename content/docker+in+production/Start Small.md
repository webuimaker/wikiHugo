---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 1  # Order that this section will appear.
title: "Start Small"
titleColor: ""
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"

---
A mistake many make when moving from running containers locally to a production environment is to expect to have it all set up from the get-go. They may imagine that they’d be able to scale to a thousand container instances right at the start without any hassles. Or they may believe that they need to have a completely microservices-based application when they move to containers in production. However, these are unreasonable expectations, and the right approach is to start from where you are, start small, and build out your ideal system over time.

While it’s easy to create a thousand container instances quickly as soon as you start, ensuring they’re all secure, well networked, and monitored is a whole other set of challenges. This is where many fail at running Docker in production.

You don’t need to have a microservices application right at the start. Legacy applications work just fine in containers. The better way is to look for low hanging fruit in your application - services that you can easily branch out from your monolith and deploy in containers separately. In some cases, a monolith can run in a container just fine. In other cases, organizations make their start in containers by deploying a new, “greenfield” application. Eventually, you’d want to move to a microservices model, but expecting to get there from the start is a recipe for failure.