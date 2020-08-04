---
# Accomplishments widget.
widget: "common"  # Widget name:  common, howto perspective, etc
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 1 # Order that this section will appear.
title: "Perspectives on Isolating Docker Containers"
subtitle: ""

# Date format
date_format: "Jan 2006"

# Accomplishments.
#   Add/remove as many `[[item]]` blocks below as you like.
#   `title`, `organization` and `date_start` are the required parameters.
#   Leave other parameters empty if not required.
#   Begin/end multi-line descriptions with 3 quotes `"""`.
item:
 - title: "Docker Security Features: User Namespace"
   summary: "The purpose of User Namespace is similar to other types of Linux namespaces - isolation. It isolates user and group ID number spaces, so that a process’s user and group ID can be different inside and outside of a user namespace."
   linkText: "https://blog.aquasec.com/docker-1.10-user-namespace"
   linkUrl: "Read the article on blog.aquasec.com »"
   openNewWindow: 
   image: "https://res.cloudinary.com/agile-seo/image/fetch/w_176,dpr_2.0,d_blank_am8gzx.png/https%3A%2F%2Flogo.clearbit.com%2Fblog.aquasec.com%3Fsize%3D250"
 - title: "Hardening Docker Hosts with User Namespaces"
   summary: "With some unchallenging configuration changes, it's possible to segregate your host's root user from the root user inside your containers with a not-so-new feature called User Namespaces. This feature has been around since Docker 1.10, which was released sometime around February 2016."
   linkText: "https://www.linux.com/blog/learn/2017/8/hardening-docker-hosts-user-namespaces"
   linkUrl: "Read the article on linux.com »"
   openNewWindow: 
   image: "https://res.cloudinary.com/agile-seo/image/fetch/w_176,dpr_2.0,d_blank_am8gzx.png/https%3A%2F%2Flogo.clearbit.com%2Flinux.com%3Fsize%3D250"

smallItem: 
 - title: "Making Containers More Isolated"
   summary: "unit42.paloaltonetworks.com"
   linkText: ""
   linkUrl: "https://unit42.paloaltonetworks.com/making-containers-more-isolated-an-overview-of-sandboxed-container-technologies/"
   openNewWindow: 
   image: "https://i-cdn.embed.ly/1/display/crop?height=300&amp;key=fd92ebbc52fc43fb98f69e50e7893c13&amp;url=https%3A%2F%2Funit42.paloaltonetworks.com%2Fwp-content%2Fuploads%2F2019%2F06%2FTrends-r3d3-1024x512.png&amp;width=636"
---

