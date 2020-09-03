---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 6  # Order that this section will appear.
title: "How to Remove an Image"
titleColor: "#000000"
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---


When you work with Docker, it's easy to accumulate excessive numbers of either untagged old images (called dangling images) or tagged but unused images, which consume unnecessary disk space.

You can remove dangling images with the `docker image prune` command. Further specifying the `-a` option in the command will remove not only the dangling images, but also all unused ones (that means an image not assigned or used in any container), regardless of their tags.






**For further reading, see Docker Documentation:** {{< read-more "docker image prune"  "https://docs.docker.com/engine/reference/commandline/image_prune/" "_blank"  >}}





