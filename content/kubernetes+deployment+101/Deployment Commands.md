---
# Accomplishments widget.
widget: "basic"  
headless: true  # This file represents a page section.
active: true  # Activate this widget? true/false
weight: 3  # Order that this section will appear.
title: "Deployment Commands"
titleColor: ""
subtitle: ""
# Date format
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format: "Jan 2006"
---


{{< table >}} 

<table>
    <tr><th>Create a deployment based on a YAML file</th></tr>
    <tr><td>kubectl create</td></tr>
</table>    


{{< /table >}}




{{< table >}} 

<table>
    <tr><th>Deploy using a phased rolling update</th></tr>
    <tr><td>kubectl rollout </td></tr>
</table>    


{{< /table >}}


{{< table >}} 

<table>
    <tr><th>Check the status of a rolling update</th></tr>
    <tr><td>kubectl rollout status   </td></tr>
</table>    


{{< /table >}}
{{< table >}} 

<table>
    <tr><th>Rollback a recent or ongoing rolling update to a previous version</th><tr>
    <tr><td>kubectl rollback   </td><tr>
</table>    


{{< /table >}}


{{< table >}} 

<table>
    <tr><th>Option to delete old replicas</th><tr>
    <tr><td>.spec.revisionHistoryLimit</td><tr>
</table>    


{{< /table >}}




