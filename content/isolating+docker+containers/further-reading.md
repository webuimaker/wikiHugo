---
# Accomplishments widget.
widget: "reading"  # See https://sourcethemes.com/academic/docs/page-builder/
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 5  # Order that this section will appear.
title: "Further Reading"
subtitle: ""

# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"

# Accomplishments.
#   Add/remove as many `[[item]]` blocks below as you like.
#   `title`, `organization` and `date_start` are the required parameters.
#   Leave other parameters empty if not required.
#   Begin/end multi-line descriptions with 3 quotes `"""`.
itemLink:

---

- **[Docker Repository Security and Certificates](/display/containers/docker+repository+security+and+certificates)**  — Docker runs via a non-networked Unix socket and TLS must be enabled in order to have the Docker client and the daemon communicate securely over HTTPS. This page gathers resources about how to ensure the traffic between the Docker registry and the Docker daemon is encrypted and a properly authenticated using certificate-based client-server authentication.
- **[Docker Trusted Image Registry](/display/containers/docker+trusted+image+registry)**  — Docker Trusted Registry (DTR) is the enterprise-grade image storage solution from Docker. It is installed behind a firewall so that Docker images can be securely stored and managed. This page gathers resources about the benefits of Docker trusted registry and how to work with it.
- **[Docker AppArmor Security Profiles](/display/containers/docker+apparmor+security+profiles)**  — AppArmor (Application Armor) is a Linux security module that protects an operating system and its applications from security threats. To use it, a system administrator associates an AppArmor security profile with each program. Docker expects to find an AppArmor policy loaded and enforced. This page gathers resources about Docker AppArmor security profiles and how to use them to enhance container security.
- **[Isolating Docker Containers](/display/containers/isolating+docker+containers)**  — Docker container technology increases the default security by creating isolation layers between applications and between the application and host and reducing the host surface area which protects both the host and the co-located containers by restricting access to the host.
- **[Docker CIS Benchmark](/display/containers/docker+cis+benchmark)**  — The Center for Internet Security (CIS) Docker Benchmark is a reference document that can be used by system administrators, security and audit professionals and other IT roles to establish a secure configuration baseline for Docker containers. This page gather resources about CIS Docker benchmark and how to implement it.