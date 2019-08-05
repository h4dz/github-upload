---
title: "Communicate Effectively with Stakeholders"
excerpt: ""
---
[block:api-header]
{
  "title": "Overview"
}
[/block]
This how-to guide covers using PagerDuty to effectively communicate with stakeholders during an incident. In addition to advising others on the impact and progress of the incident and how they are affected, proactive stakeholder communications can also lead to more efficient incident resolution, as the primary response team can focus their efforts on resolution rather than on answering continual inquiries about status.

There are several aspects to preparing for effective stakeholder communications:
  * Establishing who to inform during an incident,
  * Understanding how to manage lists of stakeholders with PagerDuty, and
  * How to send status updates to stakeholders.

The remainder of this article will cover all of these areas.
[block:callout]
{
  "type": "info",
  "body": "Many of the PagerDuty capabilities referenced in this guide are only available to customers on our Enterprise plan or with the purchase of Modern Incident Response. Please [contact our sales team](https://www.pagerduty.com/contact-sales/) if you would like to upgrade to a plan with these capabilities."
}
[/block]

[block:api-header]
{
  "title": "Who to inform"
}
[/block]
For any given incident, there are usually two factors that determine who should be considered a stakeholder:
  * What functionality, or service, is impacted?
  * What is the scope of impact?

Most organizations will have an incident classification scheme that is used to represent the impact - such as “Priority 1” through “Priority 5”, or similar. Generally speaking, the higher the incident classification, the more stakeholders are involved. For example, a Priority 3 incident with very limited customer impact might have no need for stakeholders, while a Priority 1 incident impacting a significant portion of a service’s customers might have IT management, executive leadership, and customer support as stakeholders. Some incidents may also benefit from specific additional stakeholders such as marketing, sales, or legal.

You will want to organize these stakeholders into PagerDuty teams - one team per functional area. For example, you might have the following teams of stakeholders defined:
  * IT Management Stakeholders
  * Executive Stakeholders
  * Customer Support Stakeholders
  * Sales Stakeholders

When it comes time to subscribe stakeholders to an incident, you can now pick from these defined teams rather than select many individual users one by one.

Knowing ahead of time the stakeholder teams that various kinds of incidents require will make your incident response more effective. As with many aspects of incident response, preparation is essential for making the best use of in-incident response time.
[block:callout]
{
  "type": "info",
  "body": "Any kind of PagerDuty user can be added as an incident subscriber: the account owner, managers, responders, etc. There is a special Stakeholder user license available; these users can be subscribed to incidents and receive incident status updates, and have read-only access to other data in your PagerDuty account. They cannot add, edit or delete any objects in the account. Stakeholder user licenses are available at a reduced price and are ideal for employees that need to be involved in internal incident communications but won't be actively participating in the resolution effort. Please contact our sales team for more information about Stakeholder users.",
  "title": "Stakeholder Users"
}
[/block]

[block:api-header]
{
  "title": "Automatically adding stakeholders at incident creation"
}
[/block]
You can set up PagerDuty so that certain incidents will automatically subscribe the right stakeholders when they are created. To do so: 
  1. Create a response play that subscribes users and/or teams
  2. Attach it to a PagerDuty service

Here’s an example response play that subscribes the desired stakeholder teams:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7dd5c7a-Screen_Shot_2017-12-07_at_12.18.05_PM.png",
        "Screen Shot 2017-12-07 at 12.18.05 PM.png",
        1892,
        1108,
        "#3c424c"
      ],
      "sizing": "smart"
    }
  ]
}
[/block]
Attaching this response play to a service ensures that every new incident created on the service will have the play run on it, which will subscribe the response play’s stakeholders to receive all status updates subsequently published for that incident. 

To attach a response play to a service, go to the Service page in the web app, click Edit, scroll down to Incident Settings, select the Response Play checkbox, and select your desired response play:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6cd22f5-Screen_Shot_2017-12-07_at_12.19.00_PM.png",
        "Screen Shot 2017-12-07 at 12.19.00 PM.png",
        1570,
        818,
        "#e3e5e4"
      ],
      "sizing": "smart"
    }
  ]
}
[/block]
Note that the act of subscribing stakeholders to an incident does not cause them to receive a notification. This “silent subscription” allows you to subscribe stakeholders to an incident at any time (for example, at incident creation) and then explicitly choose to publish a status update if and when there is something noteworthy to report. Thus, stakeholders receive only curated updates, which helps avoid notification fatigue.

Now that we’ve looked at effective ways to subscribe the right stakeholders to an incident, let’s look at publishing status updates to those subscribers.
[block:api-header]
{
  "title": "Subscribing stakeholders to an ongoing incident"
}
[/block]
Users and teams can be subscribed to an incident already in progress from the PagerDuty web app when looking at the incident, from the Subscribers tab:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2083d39-Screen_Shot_2017-12-07_at_11.41.28_AM.png",
        "Screen Shot 2017-12-07 at 11.41.28 AM.png",
        1902,
        928,
        "#dfe0e0"
      ],
      "sizing": "smart"
    }
  ]
}
[/block]
Usually you will want to add one or more teams as subscribers, as teams are the most effective way to manage the membership of each stakeholder group. This also lets incident response be more efficient, as selecting a team is much faster than looking up in documentation which users to include and selecting them one by one.

For some incidents you may need to add specific individuals. For example, if it is an incident that affects a particular customer, you may want to include that customer’s account manager.
[block:api-header]
{
  "title": "Adding multiple groups of stakeholders to an incident"
}
[/block]
If you frequently subscribe the same set of stakeholders to incidents, you can simplify this task by using a [response play](https://support.pagerduty.com/docs/response-automation). A response play lets you configure in advance which users and/or teams to subscribe, and then you can run that play as needed. As an example, here’s a response play for subscribing multiple stakeholder teams to an incident:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b52e30c-Screen_Shot_2017-12-07_at_12.14.44_PM.png",
        "Screen Shot 2017-12-07 at 12.14.44 PM.png",
        1354,
        690,
        "#33383f"
      ],
      "sizing": "smart"
    }
  ]
}
[/block]
Running this play on an incident is fast and efficient, and can be done from either the web app or the mobile app.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b6998f6-Screen_Shot_2017-12-07_at_12.15.38_PM.png",
        "Screen Shot 2017-12-07 at 12.15.38 PM.png",
        1894,
        906,
        "#e2e2e1"
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
        "https://files.readme.io/79f42ca-Screen_Shot_2017-12-07_at_12.16.30_PM.png",
        "Screen Shot 2017-12-07 at 12.16.30 PM.png",
        1848,
        1084,
        "#233034"
      ],
      "sizing": "smart"
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Sending status updates to incident stakeholders"
}
[/block]
As described in the [Subscriber Notifications](/docs/communicating-with-stakeholders#section-subscriber-notifications) section of the knowledge base, when a status update is published on an incident, a notification about that update is sent to all incident subscribers. Status updates can be published two different ways: a responder can compose and publish a status update ad hoc on the incident’s Subscribers tab in the web app, or they can run a response play that publishes a predefined status update.

Publishing a status update ad hoc in the web app the best choice when the content is context-dependent, for example, if a status update needs to provide details about the nature of the incident, the current impact, or the estimated resolution time:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5df6bf3-Screen_Shot_2017-12-07_at_1.34.14_PM.png",
        "Screen Shot 2017-12-07 at 1.34.14 PM.png",
        1108,
        996,
        "#dfdfde"
      ],
      "sizing": "smart"
    }
  ]
}
[/block]
In other situations the status update is less context dependent; for example, notifying about the onset of a P1 incident or announcing that the incident has been resolved. In these cases you can automate the status updates using a response play.

A response play can publish a status update in combination with subscribing stakeholders and/or adding responders. Here’s an example response play that would be suitable for attaching to a service so that whenever that service has a new incident, the identified stakeholder is subscribed and immediately receives a status update notification:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/acaba58-Screen_Shot_2017-12-07_at_1.36.42_PM.png",
        "Screen Shot 2017-12-07 at 1.36.42 PM.png",
        1650,
        802,
        "#31373f"
      ],
      "sizing": "smart"
    }
  ]
}
[/block]
Alternately, a response play such as the following can be used as a one-click wrap-up after an incident has been resolved, and could be run from either the web app or the mobile app:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0544af5-Screen_Shot_2017-12-07_at_1.37.28_PM.png",
        "Screen Shot 2017-12-07 at 1.37.28 PM.png",
        1580,
        558,
        "#26292d"
      ],
      "sizing": "smart"
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Summary"
}
[/block]
This how-to guide covered how to best use PagerDuty features together to address the primary challenges related to effective stakeholder communications during an incident. Additional information about these PagerDuty features is available in the following Knowledge Base Articles:
* [Incident subscription](/docs/communicating-with-stakeholders#section-add-subscribers-to-an-incident)
* [Teams](https://support.pagerduty.com/docs/teams)
* [Response plays](https://support.pagerduty.com/docs/response-automation)

For a detailed overview on establishing best practices, as well as more examples on how you can leverage PagerDuty’s capabilities, please refer to our Incident Response Guide. We also recommend reviewing the following how-to guides, which cover additional major incident response topics:
  * [Mobilize a Coordinated Response](https://support.pagerduty.com/docs/how-to-mobilizing-coordinated-responses)
  * [Triage Major Incidents & Integrate Your ITSM Toolchain](https://support.pagerduty.com/docs/how-to-triaging-major-incidents-integrating-your-itsm-toolchain)