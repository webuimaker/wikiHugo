---
# Homepage
title: "Docker Administration"
description: "Resources about the Docker administrative procedures such as Docker configuration, collecting Docker metrics, Docker logging and more."
titleDescription: "Resources about the <a href='/display/containers/docker+containers'>Docker</a> administrative procedures such as Docker configuration, collecting Docker metrics, Docker logging and more." 

type: "widget_page"
url: "display/containers/Docker+Administration" 
rightSide: true 
# permalink: "/display/containers/Container-Security-Management/"
# headless = true  # Homepage is headless, other widget pages are not.
active: true
breadcrumbs:
 - text: Container Technology Wiki
   url: "/"
 - text: Docker Containers
   url : "/display/containers/Docker+Containers"
 - text: Docker Administration
   url: ""
TOC: 
  enable: false
promotion:
  enable: false
  promoLogo: "/images/orellylogo.svg"
  promoBackground: "#e8f5f9"
  promoHeading: "The Container Security book by Liz Rice"
  promoSubHeading: "Fundamental Technology Concepts that Protect Containerized Applications"
  promoBtnBg: "#"
  promoBtnText: "Grab Your FREE Copy"
  promoBtnUrl: "https://info.aquasec.com/container-security-book?utm_source=wiki"
---

#  Docker Administration Topics on this Wiki

- **[Docker Configuration](/display/containers/docker+configuration)**  — After installing Docker and starting Docker, the dockerd daemon runs with its default configuration. This page gathers resources on how to customize the configuration, Docker registry configuration, start the daemon manually, and troubleshoot and debug the daemon if run into issues.
- **[Collecting Docker Metrics ](/display/containers/collecting+docker+metrics)**  — In order to get as much efficiency out of Docker as possible, we need to track Docker metrics. Monitoring metrics is also important for troubleshooting problems. This page gathers resources on how to collect Docker metrics with tools like Prometheus, Grafana, InfluxDB and more.
- **[Starting and Restarting Docker Containers Automatically](/display/containers/starting+and+restarting+docker+containers+automatically)**  — Docker provides restart policies to control whether your containers start automatically when they exit, or when Docker restarts. Restart policies ensure that linked containers are started in the correct order. This page gathers resources about how to automatically start Docker container on boot or after server crash.
- **[Managing Container Resources](/display/containers/managing+container+resources)**  — Resource management for Docker containers is a huge requirement for production users. It is necessary for running multiple containers on a single host in an efficient way and to ensure that one container does not starve the others in terms of cpu, memory, io, or networking. This page gathers resources about how to improve Docker performance by managing it's resources.
- **[Controlling Docker With systemd ](/display/containers/controlling+docker+with+systemd)**  — Systemd provides a standard process for controlling programs and processes on Linux hosts. One of the nice things about systemd is that it is a single command that can be used to manage almost all aspects of a process. This page gathers resources about how to use systemd with Docker daemon service.
- **[Docker CLI Commands ](/display/containers/docker+CLI+commands)**  — There are a large number of Docker client CLI commands, which provide information relating to various Docker objects on a given Docker host or Docker Swarm cluster. Generally, this output is provided in a tabular format. This page gathers resources about how the Docker CLI Work, CLI Tips and Tricks and basic Docker CLI commands.
- **[Docker Logging ](/display/containers/docker+logging)**  — Logs tell the full story of what is happening, or what happened at every layer of the stack. Whether it’s the application layer, the networking layer, the infrastructure layer, or storage, logs have all the answers. This page gathers resources about working with Docker logs, how to manage and implement Docker logs and more.
- **[Troubleshooting Docker Engine ](/display/containers/troubleshooting+docker+engine)**  — Docker makes everything easier. But even with the easiest platforms, sometimes you run into problems. This page gathers resources about  how to diagnose and troubleshoot problems, send logs, and communicate with the Docker Engine.
- **[Docker Orchestration - Tools and Options ](/display/containers/docker+orchestration+-+tools+and+options)**  — To get the full benefit of Docker container, you need software to move containers around in response to auto-scaling events, a failure of the backing host, and deployment updates. This is container orchestration. This page gathers resources about Docker orchestration tools, fundamentals and best practices.




