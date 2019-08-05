---
title: "Operations Best Practices: Time Based Alert Grouping"
excerpt: ""
---
#Problem Statement

Incidents in PagerDuty are containers of context for alerts. If alerts are not aggregated into an incident context, each alert generates a notification (as opposed to one notification for an incident with grouped alerts). By generating a notification for each alert associated with an incident, the danger of alert fatigue is dramatically increased.

#Best Practices

##Enable Incident and Alert Creation

On accounts created prior to November 2016, you will need to enable incident and alert creation across your services if you have not already. Navigate to each service by clicking **Configuration** :fa-arrow-right: **Services** :fa-arrow-right: **Service Name** :fa-arrow-right: **Settings** tab and selecting **Create alerts and Incidents** under **Incident Behavior**. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bf40ac7-OHMS-tbag-create-alerts-incidents.png",
        "OHMS-tbag-create-alerts-incidents.png",
        1096,
        198,
        "#f8f8f8"
      ]
    }
  ]
}
[/block]
This setting enables additional event management features such as time-based alert grouping, incident merging and service-level event suppression.  However, those event management features are only enabled if configured separately. Additional information can be found in our Knowledge Base article on [Alerts](https://support.pagerduty.com/docs/alerts). 

##Time-Based Alert Grouping

To reduce notification frequency, we recommend enabling time-based alert grouping. Alert storms are grouped into one incident per two-minute window consisting of N alerts instead of generating individual notifications for each alert. The underlying grouped alerts will still be available inside a single incident, giving you the context you need to understand the problem without unnecessary notifications. Additional details on this capability can be found in our [Knowledge Base](https://support.pagerduty.com/docs/time-based-alert-grouping).

## Expected Results

A measurable reduction in the number of notifications for your team while still ensuring responders have the context of multiple alerts.

##Risks

Unrelated alerts can be grouped into a single incident one—please review the grouped alerts to make sure nothing is missed.