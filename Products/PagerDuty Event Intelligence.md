---
title: "PagerDuty Event Intelligence"
excerpt: ""
---
PagerDuty Event Intelligence, built with automatic adaptive learning and team-centric workflows in mind, makes it easy for teams to cut through the noise so you can focus on what matters. Using PagerDuty Event Intelligence, teams can automate common manual workflows, significantly reduce operational noise, and access rich context during incident triage to speed up response.
[block:callout]
{
  "type": "info",
  "body": "PagerDuty Event Intelligence is included in our Enterprise plan. For other plans, it is a new subscription available on top of your existing PagerDuty account. Please [contact our Sales Team](https://www.pagerduty.com/contact-sales/) if you would like to upgrade to a plan with this feature suite."
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fbe2589-image4.png",
        "image4.png",
        1870,
        968,
        "#eef0ed"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Product Capabilities"
}
[/block]
The PagerDuty Event Intelligence package consists of a suite of tools: time-based alert grouping, intelligent alert grouping, similar incidents, threshold alerts, notes, and scheduled rules.  

##Alert Grouping
###Time-Based Alert Grouping

Time-Based Alert Grouping will automatically add incoming alerts into open incidents on a service to help keep you focused on the problem at hand. Once Time-Based Alert Grouping is enabled on a service, the first new incoming alert will create a new incident. Subsequent alerts will be added to that incident for the specified time period while the incident is open.

To learn more about this feature, check out our article on [Time-Based Alert Grouping](doc:time-based-alert-grouping).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/050599d-Screen_Shot_2018-06-06_at_10.44.54_AM.png",
        "Screen Shot 2018-06-06 at 10.44.54 AM.png",
        1092,
        316,
        "#f5f6f7"
      ]
    }
  ]
}
[/block]
###Intelligent Alert Grouping

Intelligent Alert Grouping allows your responders to stay focused during a storm of alerts. When enabled on a service, Intelligent Alert Grouping uses a machine-learning based algorithm to automatically group related incoming alerts into a single open incident. 

No rules or additional configuration is needed in order for this algorithm to start grouping alerts - it begins grouping automatically once enabled. Over time, the Intelligent Alert Grouping algorithm will readjust to the unique history of alerts on your service. It's a tool that gets smarter the more you use it.

Intelligent Alert Grouping weighs various factors to determine when to group alerts. This includes recurring patterns in how responders have acknowledged, resolved, and grouped incidents in the past, as well as alerts previously grouped via the Time-Based Alert Grouping feature. 

To learn more about this feature, check out our article on [Intelligent Alert Grouping](https://support.pagerduty.com/docs/intelligent-alert-grouping). 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ad9fa2e-alert_grouping_awareness.png",
        "alert_grouping_awareness.png",
        1252,
        879,
        "#f0eff0"
      ]
    }
  ]
}
[/block]
##Similar Incidents
Getting notified of an issue can be stressful – especially if the incident appears unfamiliar or new. For responders, seeing previous similar incidents adds helpful context for an accurate triage that leads to shorter resolution time. You can see whether you or someone on your team was involved in a similar incident, when these types of incidents happen, and dive into any of these incidents to discover what remediation steps were taken in the past.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/135935e-Screen_Shot_2018-06-06_at_8.31.37_AM.png",
        "Screen Shot 2018-06-06 at 8.31.37 AM.png",
        885,
        665,
        "#f6f3f4"
      ]
    }
  ]
}
[/block]
To learn more about this feature, check out our article on [Similar Incidents](doc:similar-incidents).

##Threshold Alerts
With Threshold Alerts, it is possible to receive PagerDuty notifications only when your customized alert conditions breach specified limits. In this way, responders effectively reduce alert noise without missing critical issues. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/523dda7-image3.png",
        "image3.png",
        1472,
        654,
        "#f7f7f7"
      ]
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6062e94-image6.png",
        "image6.png",
        1424,
        308,
        "#fafafa"
      ]
    }
  ]
}
[/block]
For more information about Threshold Alerts can be found in our [Global Event Routing](https://support.pagerduty.com/docs/global-event-routing#section-threshold-alerts) article.

##Adding Notes
Notes can help responders resolve incidents faster by including information or links related to the system that the event comes from. Notes are added automatically using event rules in Global Event Routing. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/84564b9-image1.png",
        "image1.png",
        1052,
        244,
        "#f4f4f4"
      ]
    }
  ]
}
[/block]
More information about Adding Notes can be found in our [Global Event Routing](https://support.pagerduty.com/docs/global-event-routing#section-adding-notes-with-event-rules) article.

##Scheduled Event Rules
You can gain a greater degree of control over your event rules by detailing a single specific time in the future in which they will be active. This is particularly helpful during rules testing and planned maintenance.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c58b1d0-image2.png",
        "image2.png",
        1458,
        920,
        "#f7f7f8"
      ]
    }
  ]
}
[/block]
For more information about Scheduled Event Rules, visit our [Global Event Routing](https://support.pagerduty.com/docs/global-event-routing#section-scheduled-event-rules) article.

##Recurring Event Rules
If there are specific hours of the day or day(s) within a week when you would like an event to follow a particular rule, you can set its activity on an automatic, weekly recurring schedule. This feature is integration-specific and you can make additional changes, such as changing severity/priority, based on time of day. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/46255eb-event-intelligence-recurring-rules.png",
        "event-intelligence-recurring-rules.png",
        1712,
        484,
        "#f9f9f9"
      ]
    }
  ]
}
[/block]
For more information about Recurring Event Rules, visit our [Global Event Routing](https://support.pagerduty.com/docs/global-event-routing#section-recurring-event-rules) article.

##Disable Event Rules
If you would like to pause an event rule’s activity, you can disable and re-enable it at a later time. This feature allows you to manually initiate integration-specific disablement during maintenance or testing on a tool. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9b31f95-event-intelligence-disable-rule.png",
        "event-intelligence-disable-rule.png",
        2192,
        420,
        "#f3f5f2"
      ]
    }
  ]
}
[/block]
For more information about Disable Event Rules, visit our [Global Event Routing](https://support.pagerduty.com/docs/global-event-routing#section-disable-event-rules) article.