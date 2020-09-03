---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 8  # Order that this section will appear.
title: "Chart Dependencies"
titleColor: ""
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---
In Helm, one chart may depend on one or more other charts. Dependencies can be dynamically linked through the `requirements.yaml` file or represented in the `charts/` subfolder within the chart directory. It might be easier to manually manage dependencies via the charts folder at first, but the recommended method is `requirements.yaml`.

The requirements.yaml file looks like this:

```
dependencies:- name: apache
version: 1.2.3
repository: http://example.com/charts
- name: mysql
version: 3.2.1
repository: http://another.example.com/charts
```

The command `helm dependency update` uses your dependency file to download all specified charts into the charts directory automatically. Dependencies are stored as compressed `.tgz` files in the charts folder.

There are many [advanced options](https://docs.helm.sh/developing_charts/#chart-dependencies) for specifying dependencies including tags, conditions and child values.
	
**For more details see Helm Documentation:** {{< read-more "Chart Dependencies" "https://docs.helm.sh/developing_charts/#chart-dependencies" "_target"  >}}	
		
		