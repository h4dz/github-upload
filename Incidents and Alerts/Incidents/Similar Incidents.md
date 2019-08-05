---
title: "Similar Incidents"
excerpt: ""
---
[block:callout]
{
  "type": "info",
  "body": "Please note that this feature is currently available as part of the [Event Intelligence](https://support.pagerduty.com/v1/docs/event-intelligence) package and Enterprise plan. If you would like to sign up for a trial of this feature and other Event Intelligence features, contact Sales at [sales@pagerdutycom](https://www.pagerduty.com/contact-us/#contact-sales). If you have any questions or would like to  share your thoughts and feedback, please reach out to our Support Team at [support@pagerduty.com](https://www.pagerduty.com/contact-us/#contact-support)."
}
[/block]

[block:api-header]
{
  "title": "Overview"
}
[/block]
Getting notified of an issue can be stressful – especially if the incident appears unfamiliar or new. For responders, seeing previous similar incidents adds helpful context for an accurate triage that leads to shorter resolution time. You can see whether you or someone on your team was involved in a similar incident, when these types of incidents happen, and dive into any of these incidents to discover what remediation steps were taken in the past.
[block:api-header]
{
  "title": "Details"
}
[/block]
Similar Incidents appears on the web application on the details page of a specific incident. The tab labeled “Similar Incidents” displays a list of historical incidents on your PagerDuty account that are similar in some way to the incident you are currently investigating. Similar incidents weighs various factors to calculate similarity between incidents, including the semantics of the incident title, how people have responded to incidents like this in the past, the duration of the incident and the date and time of the incident’s creation. 

The Similar Incidents heatmap provides a high level overview of incidents similar to the one you are viewing, that have been observed for the past six months on that service. Darker squares on the heatmap represent days when a higher concentration of similar incidents while lighter squares will have a lower concentration. The legend for the number of similar incidents will dynamically change relative to the range of similar incidents observed in a single day. 

To drill down to a specific day, you can hover over a square to view the titles of the related incidents from that day. If you click on a square, the top five similar incidents from that day will populate below in the Similar Incidents list. You can then easily access those incidents for additional context by clicking on the linked incident title
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c0fa25b-Screen_Shot_2018-06-06_at_8.31.24_AM.png",
        "Screen Shot 2018-06-06 at 8.31.24 AM.png",
        887,
        678,
        "#f7f6f6"
      ],
      "caption": "Similar Incidents View with Heat Map",
      "sizing": "full"
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/04ef325-Screen_Shot_2018-06-06_at_8.31.37_AM.png",
        "Screen Shot 2018-06-06 at 8.31.37 AM.png",
        885,
        665,
        "#f6f3f4"
      ],
      "caption": "Similar Incidents view with details shown - click on a square on the heat map to focus on that day."
    }
  ]
}
[/block]
The Similar Incidents list displays the historical, similar incidents with specific metadata fields and links. For each historically similar incident, you can see the incident title, the duration of the incident, the date the incident was created, and the person who last changed this incident. 

**Title:** The incident title in its current state. If the incident title was manually edited, the final title will be displayed here. 

**Duration:** Duration of the incident.

**Created:** Date and time the incident was created.

**Last Changed By:** PagerDuty user who last made a change to this incident. If this incident was not edited by any PagerDuty user, this field will be blank, “--”. This can happen, for example, if the incident was triggered and then resolved by the underlying monitoring tools. 

Currently there are no configuration options for Similar Incidents. We welcome your comments and feedback for what you would like to configure about Similar Incidents. The PagerDuty Data Experience team is iterating on the designs and underlying algorithm.
[block:api-header]
{
  "title": "Things to keep in mind"
}
[/block]
1. Similar Incidents will only return incidents from the same service as the incident you are viewing.

2. Similar Incidents are only visible from the PagerDuty web application in the current state.
 
3. If you would like to hide Similar Incidents, please contact PagerDuty support.

[block:api-header]
{
  "title": "FAQ"
}
[/block]
***Can I tell the system that this incident is not similar if it appears in the list of Similar Incidents?***

At the moment, no. The PagerDuty Data Experience team would love to hear your feedback about which incidents would be more useful to you and which incidents were not helpful to see in the Similar Incidents tab. 

***How is this different from alert grouping?***

While alert grouping combines alerts that are currently part of the same incident, Similar Incidents looks at related incidents from any point in time to help users get the context needed to resolve an incident. 

***Do suppressed alerts show up in Similar Incidents?*** 

Nope! The goal of Similar Incidents is to show relevant, related incidents from your incident management history. If you’ve decided to suppress alerts on a service, those alerts will not be part of your service’s history.  We take that as an indication that those alerts are not relevant to your current incident and therefore will not be displayed under Similar Incidents.

***Can I see Similar Incidents when I write up my post mortems?***

At the moment, no, but it’s a request we’ve heard! While Similar Incidents are not currently an explicit part of the [post mortem builder](https://support.pagerduty.com/docs/postmortems), you can always use information from Similar Incidents to help add context to the post mortem.