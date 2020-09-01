---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 3  # Order that this section will appear.
title: "How Containers Communicate with Each Other"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---

Different networks provide different communication patterns (for example by IP address only, or by container name) between containers depending on network type and whether it’s a Docker default or a user-defined network.

## Container discovery on docker0 network (DNS resolution)

Docker will assign a name and hostname to each container created on the default `docker0` network, unless a different name/hostname is specified by the user. Docker then keeps a mapping of each name/hostname against the container’s IP address. This mapping allows pinging each container by name as opposed to IP address.

Furthermore, consider the following example which starts a Docker container with a custom name, hostname and DNS server:

`$ docker run --name test-container -it \
--hostname=test-con.example.com \
--dns=8.8.8.8 \
ubuntu /bin/bash`


In this example, processes running inside `test-container`, when confronted with a hostname not in `/etc/hosts`, will connect to address 8.8.8.8 on port 53 expecting a DNS service.


**For further reading, see Kubernetes Documentation:** {{< read-more "Embedded DNS server in user-defined networks" "https://docs.docker.com/engine/userguide/networking/configure-dns/" "_target"  >}}
  
  
  
## Directly linking containers
It is possible to directly link one container to another using the `--link` option when starting a container. This allow containers to discover each other and securely transfer information about one container to another container. However, Docker has deprecated this feature and recommends creating user-defined networks instead.

As an example, imagine you have a `mydb` container running a database service. We can then create an application container named `myweb` and directly link it to `mydb`:

`$ docker run --name myweb --link mydb:mydb -d -P myapp python app.py`


**For further reading see Docker Documentation:** {{< read-more "Legacy container links" "https://docs.docker.com/engine/userguide/networking/default_network/dockerlinks/" "_target"  >}}






