---
title: "Dynamic Notifications"
excerpt: ""
---
[block:callout]
{
  "type": "info",
  "title": "Accessing this feature",
  "body": "Legacy Lite and Basic plans do not have access to Dynamic Notifications. If you would like to use to this feature, please [contact our Sales team](https://www.pagerduty.com/contact-sales/) to switch to any of our current plans."
}
[/block]

[block:api-header]
{
  "title": "Event/Alert Severity Levels"
}
[/block]
Alerts in PagerDuty can be generated with a severity field. These severity values can be directly provided from the triggering monitoring tool, or set using event rules.

When an incident is generated from an alert, the alert’s severity field is used to determine the urgency level. The values of this field must be one of the following: `critical`, `error`, `warning`, or `info`. Note that this is case sensitive, so `Info` will not work. Urgency mapping works as follows:
[block:parameters]
{
  "data": {
    "h-0": "Alert Severity",
    "h-1": "Description",
    "h-2": "Default Incident Urgency",
    "h-3": "Incident Behavior",
    "0-0": "`critical`",
    "0-1": "A failure in the system's primary application.",
    "0-2": "High",
    "0-3": "Uses high-urgency notification rules and escalates if not acknowledged.",
    "1-0": "`error`",
    "1-1": "Any error which is fatal to the operation, but not the service or application.",
    "1-2": "High",
    "1-3": "Uses high-urgency notification rules and escalates if not acknowledged.",
    "2-0": "`warning`",
    "2-1": "May indicate that an error will occur if action is not taken.",
    "2-2": "Low",
    "2-3": "Uses low-urgency notification rules and does not automatically escalate.",
    "3-0": "`info`",
    "3-1": "Normal operational messages that require no action.",
    "3-2": "Low (if appended to an incident; we recommend suppressing info alerts)",
    "3-3": "Uses low-urgency notification rules and does not automatically escalate.",
    "4-0": "*Unknown*",
    "4-1": "Automatically chosen when a monitoring tool is not setting or can not set the severity",
    "4-2": "High",
    "4-3": "Uses high-urgency notification rules and escalates if not acknowledged."
  },
  "cols": 4,
  "rows": 5
}
[/block]
Severity to Urgency mappings are hard-coded (as shown below). Any incoming events that do not contain a Severity will default to High Urgency.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4f21b54-Screen_Shot_2017-08-09_at_3.39.59_PM.png",
        "Screen Shot 2017-08-09 at 3.39.59 PM.png",
        1068,
        445,
        "#e7ebeb"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Using Severity to Control Urgency"
}
[/block]
In order to use this capability, go to a Service’s settings page and switch **“How should responders be notified”** to “Use alert severity to determine how responders are notified for each incident”:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e4846d9-Screen_Shot_2017-08-09_at_3.42.26_PM.png",
        "Screen Shot 2017-08-09 at 3.42.26 PM.png",
        1228,
        339,
        "#e9ecec"
      ]
    }
  ]
}
[/block]
Any alert-created incidents on the service will now determine their notification urgency according to the Severity of the alerts that create them. When an alert is added to an incident, or when an alert’s severity changes, it will also update its corresponding incident’s Notification Urgency, but only upward. For example, an alert changing from Warning to Critical will change the associated incident from Low to High, but another change from Critical to Warning will not down-urgency the incident.

Non-alert incidents, such as those manually triggered or triggered through the Create Incidents API, will always have their urgency set by the service’s setting. 
[block:api-header]
{
  "title": "Defined Support Hours"
}
[/block]
Users can also take advantage of Dynamic Notifications in relation to [defined support hours](https://support.pagerduty.com/v1/docs/service-settings#section-use-case-2-support-hours) on a service. Defined support hours can be configured by editing the settings on the service in question.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/06e98d3-Screen_Shot_2017-08-09_at_3.44.33_PM.png",
        "Screen Shot 2017-08-09 at 3.44.33 PM.png",
        1152,
        490,
        "#eef0f0"
      ]
    }
  ]
}
[/block]
Customers can also base their Notification Urgencies off of time of day. Here, the user can set specific support hours, and decide how they want to be notified inside and outside of this time window. The user can select either High, or Low, or Dynamic Notifications. When support hours end, users also have the option to either leave Incidents at their current Urgency, or raise the Urgency of all triggered incidents for the Service to High.
[block:api-header]
{
  "title": "Upgrading Incident Notification Urgency"
}
[/block]
If multiple trigger events come in for the same alert, the alert will upgrade its severity value to the most severe value. For example, if an alert was initially triggered by a Warning event, but then a Critical event comes in, the alert will now be Critical, and the associated incident will change from low urgency to high urgency. If a subsequent Info event comes in, the incident will remain High Urgency. It will not downgrade to Low. 

There are three ways in which multiple alerts can be “bundled” into a single incident. First is by using our [Alert Grouping](https://support.pagerduty.com/docs/time-based-alert-grouping) feature. Here, users can group alerts for a set period of time, or until the incident resolves. While Grouping is activated, subsequent alerts will roll-up under the single incident. The incident will adopt the Notification Urgency that corresponds with the most severe alert that is grouped with it.

The second way alerts can be "bundled" is by manually merging their parent incidents. Below is an example of two alerts that have been merged into a single incident. In this example, the urgency of the first alert was raised to **High** by the merge:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8b75f13-raised_urgency.png",
        "raised_urgency.png",
        1236,
        582,
        "#ecebea"
      ]
    }
  ]
}
[/block]
The third way alerts can be “bundled” to a single incident is using a alert dedup_key. Using a dedup_key, a subsequent alert trigger will replace an existing alert. 
[block:api-header]
{
  "title": "PagerDuty Common Event Format"
}
[/block]
For integrations already mapped to the PagerDuty Common Event Format (PD-CEF), alerts of varying severities may be generated by default. For most integrations, however, alerts are generated as Critical by default, and event rules must be used to set the desired severity.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8139668-Screen_Shot_2017-07-18_at_10.22.39_AM.png",
        "Screen Shot 2017-07-18 at 10.22.39 AM.png",
        924,
        490,
        "#ebebeb"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Recommended Practices"
}
[/block]
**For immediately actionable events, set a “critical” or “error” severity.**

This will ensure that any associated incidents use high-urgency notification channels and escalate if not acknowledged.

**For actionable events that do not require immediate attention, set a “warning” severity.**

This will create a low-urgency incident that does not escalate.

**For non-actionable events, consider suppressing them in addition to setting an “info” severity.**

Non-actionable events do not require incident response, so in most cases you will want to suppress these.
[block:api-header]
{
  "title": "Frequently Asked Questions"
}
[/block]
**How does this interact with Incident Priority?**

Incident Priority and Incident Urgency are separate properties that today, do not influence each other. Currently, “Priority” can be set manually by users on an existing incident or during incident creation via manual creation or the Incident Create API. In the future, the event rules might have the capability to set Priority based on criteria set by the user, but this work is currently unplanned. 

**What if an alert does not have a severity attached?**

Alerts created prior to November 2016 may not have severity information attached. However, since then, all alerts are generated with severity, and default to Critical if the severity is not specified by the emitting system, by event transformer, or by an event rule. Events sent to the new Events API v2 must have severity specified.

**What about Email Integrations?**
Email Integrations will also not send in Severity. We are currently scoping out work to allow users to set Severity for email integrations.

**Can I customize the mapping of severity to urgency?**

As of the current date, mappings are not customizable. We intend to build this capability into the platform in future iterations of this feature.

**How do I set urgency if the monitoring tools does not sent it to PD?**

You can use the Event Rules engine to set a Severities for incoming alerts on a Service.

**How does this relate to PagerDuty CEF?**

Integrations mapped to CEF will automatically send in Severity. Users can always send in Severity information using the Events API v2.

**How does this relate to Alert Grouping?**

Users can group alerts into a single incident, either over a specific time period, or for as long as the incident is open. As new alerts bundle into an incident, we will upgrade the incident Urgency to the most severe alert. We will never downgrade an incidents Urgency.

**Will Incident Log Entries Update?**

Yes, we update the ILEs to indicate when incident Urgency is set by Severity, and when incident Urgency is upgraded due to alert Severity.