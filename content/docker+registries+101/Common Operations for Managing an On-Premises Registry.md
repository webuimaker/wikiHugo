---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 6  # Order that this section will appear.
title: "Common Operations for Managing an On-Premises Registry"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
Common operations necessary to manage an on-premises registry installation include:

* <strong>Start registry:</strong> The registry is itself a Docker image that needs to be run as a container using `docker run` . For example, to run it based on the default configuration and forwarding requests on host port 5001 to container port 5000 (the default port the registry will listen to):

```
docker run -d -p 5001:5000 --name registry registry:2
```

By default, registry data is persisted as a Docker volume. To specify a particular storage location on the host (for example, an SSD or SAN filesystem) use the bind mount option:

```
-v <host location>:<container location>
```

* <strong>Automatically restart registry:</strong> To keep the registry running when the host restarts or simply because the registry container stopped, simply add the option `--restart=always` to the command.

* <strong>Stop registry:</strong> Stopping the registry is simply a matter of stopping the running registry container with `docker stop registry` command. To actually remove the container also run:

```
docker rm -v registry
```

Note that the open source Docker registry comes with a set of default configurations for logging, storage, authentication, middleware, reporting, http, notifications, health checks and more.

 These can be overridden individually by passing in specific environment variables to the registry start command. For example, the following command tells the registry to listen for requests on the container’s port 5001 instead of default port 5000.

```
docker run -d -e REGISTRY_HTTP_ADDR=0.0.0.0:5001 -p 5001:5001 \
--name registry registry:2
```

The other option is to completely override the configuration settings with a YAML file . Also it needs to be mounted as a volume on the container, for example:

```
docker run -d -p 5001:5000 -v config.yml:/etc/docker/registry/config.yml \
--name registry registry:2
```





**For further reading, see Docker Documentation:** {{< read-more " Deploy a registry server"  "https://docs.docker.com/registry/deploying/" "_blank"  >}} and {{< read-more " Configuring a registry"  "https://docs.docker.com/registry/configuration/" "_blank"  >}}




