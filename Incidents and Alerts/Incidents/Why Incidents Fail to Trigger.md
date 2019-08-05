---
title: "Why Incidents Fail to Trigger"
excerpt: ""
---
[block:api-header]
{
  "title": "Why was an Incident not Triggered or Created?"
}
[/block]
There are a few reasons why an incident would not be triggered or created in PagerDuty:
- [A Service was Disabled or Placed in Maintenance Mode](#section-a-service-was-disabled-or-placed-in-maintenance-mode)
- [Email Integration Settings are Filtering out Emails](#section-email-integration-settings-are-filtering-out-emails)
- [Email Management Rules are Appending Triggers to Existing Incidents](#section-email-management-rules-are-appending-triggers-to-existing-incidents)
- [Nobody was On-call](#section-nobody-was-on-call) 
[block:api-header]
{
  "title": "A Service was Disabled or Placed in Maintenance Mode"
}
[/block]
When a service is [disabled](/docs/maintenance-windows#section-disable-a-service) or in [maintenance mode](/docs/maintenance-windows#section-scheduling-maintenance), new incidents will not be triggered or created for that service. Because an incident is not created, PagerDuty will not send notifications to the person on-call for that service.
[block:api-header]
{
  "title": "Email Integration Settings are Filtering out Emails"
}
[/block]
If you have regex filters set up on your email integration service, then you will want to check to make sure that your regex filters are not [filtering out emails](doc:email-management-filters-and-rules#section-limit-noise-with-email-integration-filters) that you want to trigger incidents.

For example, if you have the following regex filter:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/86a4550-edit_service_regex_critical.png",
        "edit_service_regex_critical.png",
        1465,
        509,
        "#f3f3f2"
      ]
    }
  ]
}
[/block]
Then emails with the subject line "PROBLEM" will not trigger incidents in PagerDuty, because they are filtered out based on your regex rules.
- [View some regular expression examples](/docs/email-management-filters-and-rules#section-regular-expression-tips-examples)
- [Test your regular expressions with Rubular](http://rubular.com/)
[block:api-header]
{
  "title": "Email Management Rules are Appending Triggers to Existing Incidents"
}
[/block]
Email integration settings also have email management rule settings. These are distinct from email filters. While email filters determine which emails trigger incidents for your service, incident creation settings determine how emails create new incidents. 

If you have either of these two email management rules for your email integration service:
- **Open a new alert only if an open incident does not already exist**
- **Open and resolve alerts based on custom rules**

...then an incident was most likely appended to an existing incident, which would explain why a new incident was not created. [Learn more about incident creation settings](/docs/email-management-filters-and-rules#section-trigger-and-resolve-alerts-with-email-management-rules).

When a trigger is appended to an incident it will look like the following. The appended trigger is highlighted in green. Notice that both triggers are appended to the same incident, appearing in the same incident timeline.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/407fc4f-append.png",
        "append.png",
        906,
        479,
        "#f7f8f7"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Nobody was On-call"
}
[/block]
If no one is on-call on a service's escalation policy, PagerDuty does not have a user to assign an incident to, and we will not create a new incident. 

For example, if your escalation policy only has the following schedule associated with it, where one user is on-call from 00:00 - 08:00, if a trigger comes in between 08:01 - 23:59, no new triggers will be created in PagerDuty because no one will be on-call.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cc3476a-Screen_Shot_2017-03-17_at_9.48.28_AM.png",
        "Screen Shot 2017-03-17 at 9.48.28 AM.png",
        1160,
        611,
        "#efefef"
      ]
    }
  ]
}
[/block]
To address this, check the [escalation policy](doc:escalation-policies) associated with your service and make sure that someone will be on-call when you need incidents to trigger.
[block:callout]
{
  "type": "info",
  "body": "If you try to trigger a new incident through the website while nobody is on-call on the escalation policy associated with that service, you will receive the error **Incident could not be created**.",
  "title": "Note"
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/238ede4-could_not_create_incident.png",
        "could_not_create_incident.png",
        553,
        459,
        "#f0e7e6"
      ]
    }
  ]
}
[/block]