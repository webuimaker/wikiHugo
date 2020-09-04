---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 4  # Order that this section will appear.
title: "How Do They Differ from Docker"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---

Let us take a quick look at how each of these alternatives differs from Docker:

{{< table >}}
    <table>
        <tr>
            <th>
            </th>
            <th>Rkt
            </th>
            <th>LXD
            </th>
            <th>OpenVZ
            </th>
            <th>LinuxVServer
            </th>
            <th>Windows Containers
            </th>
        </tr>
        <tr>
            <th>Compared to Docker</th>
            <td>Focuses on compatibility, hence it supports multiple container formats, including Docker images and its own format. Like Docker, it is optimized for application containers, not full-system containers and has fewer third-party integrations available.
            </td>
            <td>Emulates the experience of operating Virtual Machines but in terms of containers and does so without the overhead of emulating hardware resources. While the LXD daemon requires a Linux kernel it can be configured for access by a Windows or macOS client.
            </td>
            <td>An extension of the Linux kernel, which provides tools for virtualization to the user. It uses Virtual Environments to host Guest systems, which means it uses containers for entire operating systems, not individual applications and processes.
            </td>
            <td>Uses a patched kernel to provide operating system-level virtualization features. Each of the Virtual Private Servers is run as an isolated process on the same host system and there is a high efficiency as no emulation is required. However, it is archaic in terms of releases, as there have been none since 2007.
            </td>
            <td rowspan ="4">The <a href="/display/containers/docker+on+windows">Docker Engine for Windows</a> Server 2016 directly accesses the windows kernel. Hence native Docker containers cannot be run on Windows Containers. Instead, a different container format, WSC (Windows Server Container), is to be used.
            </td>
        </tr>        
        <tr>
            <th>Use Cases</th>
            <td>Public cloud portability, Stateful app migration, and Rapid Deployment.
            </td>
            <td>Bare-metal hardware access for VPS, multiple Linux distributions on the same host.
            </td>
            <td>CI/CD and DevOps, Containers and big data, Hosting Isolated Set of User Applications, Server consolidation.
            </td>
            <td>Multiple VPS Hosting and Administration, and Legacy support.
            </td>
        </tr>
        <tr>
            <th>Adoption</th>
            <td>Moderate.
            </td>
            <td>Low.
            </td>
            <td>Low.
            </td>
            <td>Low - Moderate (Mostly Legacy Hosting).
            </td>
        </tr>
        <tr>
            <th>Used By</th>
            <td >CA Technologies, Verizon, Viacom, <a href="http://salesforce.com/"  target="_blank">Salesforce.com</a> <span>, DigitalOcean, BlaBlaCar, Xoom.</span></td>
            <td>Walmart PayPal, Box.
            </td>
            <td>FastVPS, Parallels, Pixar Animation Studios, Yandex.
            </td>
            <td>DreamHost, Amoebasoft, OpenHosting Inc., Lycos, France, Mosaix Communications, Inc.
            </td>
        </tr>


    </table>

{{< /table >}}






As the various Docker alternatives mentioned move ahead with rooting out bugs, increasing security, extending functionality, and adding new features, we will also have service providers offering hosting options, even more, agile development options, distributed applications, and microservices.



One of the directions that these platforms would be heading towards is better support, tools, and strategies for containerizing legacy applications. We also have a consortium of companies like the [Cloud Native Computing Foundation](https://www.cncf.io/) that is driving innovation across such projects as well as incubating new projects centered around these platforms and services. Among the various [container runtimes](/display/containers/container+runtime+interface) discussed above, rkt and [containerd](/display/containers/Containerd) have been accepted as [ongoing projects](https://www.cncf.io/projects/) by the [Cloud Native Computing Foundation](/display/containers/cloud+native+computing+foundation).



As you can see, there may be many container runtimes available. This is a good thing, as it promotes innovation and gives developers a range of tools to suit their specific needs, while still having consolidation around Docker itself. Hopefully, this article has you thinking about what container format you would use for your next application.







**For more details, see the Swarm documentation:** {{< read-more "Run Docker in Swarm mode"  "https://docs.docker.com/engine/swarm/swarm-mode/" "_blank"  >}}

