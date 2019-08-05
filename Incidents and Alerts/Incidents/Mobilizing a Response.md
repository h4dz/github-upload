---
title: "Mobilizing a Response"
excerpt: ""
---
[block:api-header]
{
  "title": "Add Responders"
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "This feature is available to customers on our Enterprise plan and as part of the [Modern Incident Response](https://support.pagerduty.com/docs/pagerduty-modern-incident-response) package. Please contact our [Sales Team](https://www.pagerduty.com/contact-sales/) if you would like to upgrade to a plan featuring Response Mobilizer."
}
[/block]
Adding responders enables you to receive assistance from additional users with an incident response. Typical reasons for adding responders include sev-1 responses, critical incident responses, and mobilizing teams. 

You can request **individual users** or **escalation policies** as responders, with a limit of 300 Responders per incident. The requested users will have the option to accept or decline the request to respond to the incident.

##Add Responders to an Incident

A user, who can take action on the **open** incident, can request responders within the web UI and mobile app.

In the web UI:
1. Within the incident details of **open** incidents, by clicking the **Add Responders** button

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5b17594-e992b12-incident-details.png",
        "e992b12-incident-details.png",
        2594,
        1228,
        "#eeeeee"
      ]
    }
  ]
}
[/block]
2. While **manually** triggering an incident, by clicking the **Create New Incident** button at the top right within the **Incidents** page or within a **Service** page.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a3079fc-9337f81-manual-trigger-incident.png",
        "9337f81-manual-trigger-incident.png",
        1236,
        1434,
        "#d8d8d7"
      ]
    }
  ]
}
[/block]
In the mobile app:
1. **iOS:** Select an **open** incident, click the **More** button at the bottom right, and select the **Add Responder** button.
2. **Android:** Select an **open** incident, click the three horizontal dots at the top right, and click the **Add Responder** button.

**Note:** You can add a conference bridge address in the initial request sent to responders.

## Responders Notifications

As a responder, you’ll receive the request to join an incident response on each of your **contact methods** used by your **high-urgency notification rules** which have the** lowest notification delay**. 

**Note:** Joined responders **do not receive additional incident notifications** after accepting the request.

## Status of Responders 

To view the status of **all requested responders** for an incident, head to the incident details section of the particular incident in the web UI. On the right-hand side within the incident, there will be a list of responders and icons to indicate whether they have joined, declined, or have yet to respond to your request.

There are 3 possible responder statuses: **Joined** if the requested responder accepted the request, **Declined** if they declined the request, and **Pending** if they have yet to respond. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a287fbd-2f94bdb-responder-widget.png",
        "2f94bdb-responder-widget.png",
        900,
        920,
        "#ececeb"
      ],
      "caption": "In this example, Jay has Joined the incident response, Tony has Declined the request, and Jack has yet to respond to the request"
    }
  ]
}
[/block]
In the timeline of the incident in the web UI, you can see when a requested responder accepted or declined the request. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9a078c6-b9926e0-timeline.png",
        "b9926e0-timeline.png",
        1932,
        368,
        "#edeeee"
      ],
      "caption": "In this example, Tony Declined the request at 9:18 by SMS"
    }
  ]
}
[/block]
In the mobile app, additional responders have been requested if you see **Coordinated Response** next to an incident. You can also view if a responder has **joined** or **declined** the request within the timeline of the incident.

## Adding Responders at Scale

For repeatable, automated mobilization of responders, you can make use of a **Response Play**. Response plays are packaged incident actions, and adding responders is one component. You can read further about the response plays feature [here.](/docs/response-automation)

Mobilizing a coordinated and cross-functional response can sometimes be a complicated task. Check out [our guide](/docs/how-to-mobilizing-coordinated-responses) on the fundamentals of a coordinated incident response.

# Other Features to Facilitate Incident Response

Instead of adding responders for additional assistance to the incident at hand, you can: 

* [Communicate with Stakeholders](/docs/communicating-with-stakeholders) which lets you **notify stakeholders** who aren't directly involved with resolving the incident. 
* [Escalating or Delegating an Incident](/docs/reassigning-and-delegating-incidents) which **re-assigns** the incident resolution responsibilities to another user.