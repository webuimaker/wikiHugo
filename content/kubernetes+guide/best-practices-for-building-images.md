---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 7  # Order that this section will appear.
title: "Best Practices for Building Images"
titleColor: "#003366"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"

---

The following best practices are recommended when you build images by writing Dockerfiles:

- **Containers should be ephemeral** in the sense that you can stop or delete a container at any moment and replace it with a new container from the Dockerfile with minimal set-up and configuration.  
- Use a **.dockerignore** file to reduce image size and reduce build time by excluding files from the build context that are unnecessary for the build. The **build context** is the full recursive contents of the directory where the Dockerfile was when the image was built.
- **Reduce image file sizes** (and attack surface) while keeping Dockerfiles readable by applying either a {{< target-blank "builder pattern  or a  multi-stage build" "https://docs.docker.com/engine/userguide/eng-image/multistage-build">}}   (available only in Docker 17.05 or higher).
- With a **builder pattern**, you maintain two Dockerfiles – one to build an application inside the image and a second Dockerfile that includes only the resulting application binaries from the first image to generate a second, streamlined image that is production ready. This pattern requires a custom script in order to automatically apply the transformation from the “development” image to the “production” image (for an example, see the Docker documentation: {{< target-blank "Before Multi-Stage Builds" "https://docs.docker.com/engine/userguide/eng-image/multistage-build/#before-multi-stage-builds">}}  ).
- **A multi-stage build** allows you to use multiple FROM statements in a single Dockerfile and selectively copy artifacts from one stage to another, leaving behind everything you don’t want in the final image. You can, therefore, reduce image file sizes without the hassle of maintaining separate Dockerfiles and custom scripts when using the builder pattern.
- **Don't install unnecessary packages** when building images.
- **Use multi-line commands instead of multiple RUN commands** for faster builds when possible (for example, when installing a list of packages).
- **Sort multi-line lists of packages into alphanumerical order** to easily identify duplicates and make it easier to update and review the list.
- **Enable content trust** when operating with a remote Docker registry so that you can only push, pull, run, or build trusted images which have been digitally signed to verify their integrity. When you use Docker with content trust, commands only operate on tagged images that have been digitally signed. Less trustworthy unsigned image tags are invisible when you enable content trust (off by default). To enable it, set the DOCKER_CONTENT_TRUST environment variable to 1. For further information see the Docker documentation: {{< target-blank "Content trust in Docker" "https://docs.docker.com/engine/security/trust/content_trust/">}}  .

**For further reading, see Docker Documentation:** {{< read-more "Best Practices For Writing Dockerfiles" "https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/" "_blank" >}}

**Read more on this wiki:** {{< read-more "Docker Images 101" "/display/containers/Docker+Images+101"  >}}