---
title: "Common Event Format (PD-CEF)"
excerpt: ""
---
The PagerDuty Common Event Format (PD-CEF) is a standardized alert format that allows us to correlate similar items across integrations and better understand the events from your environment. PD-CEF also allows you to view alert and incident data in a cleaner, more normalized way. You can also use PD-CEF to dynamically suppress non-actionable alerts using [Event Rules](doc:event-management#section-suppression-and-event-rules).

PD-CEF details display at the top of alert and incident detail pages. They express common operations event concepts in a normalized, readable way.

Within the [alerts table](https://support.pagerduty.com/docs/alerts#section-alerts-table), the PD-CEF fields Severity, Summary, Source, Class, Component, and Group can be viewed in relation to your alerts. To customize the fields shown on this page, click the **Customize Columns** button on the right side.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/286c606-common-event-format-alerts-table.png",
        "common-event-format-alerts-table.png",
        1379,
        686,
        "#e5e7ea"
      ]
    }
  ]
}
[/block]
## PD-CEF Fields

PD-CEF details map to the following fields. The table below outlines the name, type, and description of each value, as well as an example value for each. 
[block:parameters]
{
  "data": {
    "h-0": "Name",
    "h-1": "Type",
    "h-2": "Example Value",
    "0-0": "**Summary**",
    "0-1": "String",
    "h-3": "Usage",
    "0-3": "A high-level, text summary message of the event. Will be used to construct an alert's description.",
    "0-2": "\"PING OK - Packet loss = 0%, RTA = 1.41 ms\"w\n\"Host 'acme-andromeda-sv1-c40 :: 179.21.24.50' is DOWN\"",
    "1-0": "**Source**",
    "1-1": "String",
    "1-2": "\"prod05.theseus.acme-widgets.com\"\n\n\"171.26.23.22\"\n\n\"aws:elasticache:us-east-1:852511987:cluster/api-stats-prod-003\"\n\n\"9c09acd49a25\"",
    "1-3": "Specific human-readable unique identifier, such as a hostname, for the system having the problem.",
    "2-0": "**Severity**",
    "2-1": "Enum {Info, Warning, Error, Critical}",
    "2-2": "Info, Warning, Error, Critical",
    "2-3": "How impacted the affected system is. Displayed to users in lists and influences the priority of any created incidents.",
    "3-0": "**Timestamp** ",
    "3-1": "Timestamp",
    "3-2": "2015-07-17T08:42:58.315+0000",
    "3-3": "When the upstream system detected / created the event. This is useful if a system batches or holds events before sending them to PagerDuty.",
    "4-0": "**Class** ",
    "4-1": "String",
    "4-2": "\"High CPU\"\n\n\"Latency\"\n\n\"500 Error\"",
    "4-3": "The class/type of the event.",
    "5-0": "**Component** ",
    "5-1": "String",
    "5-2": "\"keepalive\"\n\n\"webping\"\n\n\"mysql\"\n\n\"wqueue\"\n\n\"LOAD_AVERAGE\"",
    "5-3": "The part or component of the affected system that is broken.",
    "6-0": "**Group**",
    "6-1": "String",
    "6-2": "[\"production-app-stack\"]\n\n\"prod-datapipe\"\n\n\"www\"\n\n\"web_stack\"",
    "6-3": "A cluster or grouping of sources. For example, sources “prod-datapipe-02” and “prod-datapipe-03” might both be part of “prod-datapipe”",
    "7-0": "**Custom Details**",
    "7-3": "Free-form details from the event.",
    "7-2": "{\"ping time\": \"1500ms\", \"load avg\": 0.75 }",
    "7-1": "Object"
  },
  "cols": 4,
  "rows": 8
}
[/block]
## PD-CEF fields as they appear on an individual alert
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8168ebd-alert_PD_CEF-1.png",
        "alert PD CEF-1.png",
        1115,
        640,
        "#ebf5e9"
      ]
    }
  ]
}
[/block]
## Events API v2

The Events API v2 offers an easier way to leverage PD-CEF fields in your alerts. Monitoring partners can now directly send in the PD-CEF format, giving you the benefit of the format without needing to manually convert your events. Custom monitoring can also leverage this format, to take advantage of the new PD-CEF display and workflow features in PagerDuty. 

Review our [developer docs](https://v2.developer.pagerduty.com/docs/events-api-v2) for more information about the Events API v2 and how to use it.

PD-CEF is currently available for the following integrations:

* AWS Cloudwatch
* Azure
* Datadog
* Github
* Hipchat
* Logic Monitor
* Microsoft OMS
* Nagios
* New Relic
* Pingdom
* PRTG
* Sensu
* Slack
* Splunk
* Wormly
* Zabbix