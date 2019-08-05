---
title: "Mobilize a Coordinated Response"
excerpt: ""
---
[block:api-header]
{
  "title": "Overview"
}
[/block]
A coordinated response is a cross-functional team of incident responders whose primary goal is to efficiently restore service for those impacted. Whether handling a major incident that requires the expertise and bandwidth of multiple responders to drive fast resolution, or navigating a lower impact but complex situation that needs input from multiple parties, effective coordinated response is an essential practice for efficient operations management.

Each coordinated response has the following steps:

* Identify who is needed. The scope of impact, and who is affected, will usually determine this. Most organizations have a set of response teams that are used over and over.
* Establish a collaboration channel. This will be one or more of a conference bridge, a video call, a chat room, or a physical war room where responders will gather to collaborate. It’s important to know whether you will be re-using the same bridge/call/chat/room for all responses, or will be using a new collaboration channel for each response.
* Engage responders. This involves quickly and accurately engaging responders to fill the needed roles.

This article will review the fundamentals of coordinated responses, how to prepare your organization to make use of them, and how to best leverage PagerDuty capabilities for effective mobilization of coordinated responses.
[block:callout]
{
  "type": "info",
  "body": "Many of the PagerDuty capabilities referenced in this guide are only available to customers on our Enterprise plan or with the purchase of Modern Incident Response. Please [contact our sales team](https://www.pagerduty.com/contact-sales/) if you would like to upgrade to a plan with these capabilities."
}
[/block]

[block:api-header]
{
  "title": "Who is involved in a coordinated response?"
}
[/block]
A coordinated response for a major incident will typically involve the following core roles:

* Incident commander: every coordinated response benefits from someone whose entire role is driving the response team’s efforts towards successful incident resolution. In some organizations this role is referred to as an incident manager.
* Subject matter experts (SMEs): These are the responders who are knowledgeable about the systems involved in the incident, and focus their entire effort toward resolving the underlying issue (sometimes referred to as “resolvers”) to distinguish their role from others involved in the response. There are often multiple SMEs for a given coordinated response, and its typical that they would be drawn from different technical teams, providing the skills and knowledge necessary for the specific incident at hand.
* Non-resolver responders: these are responders with a specialized function outside of the domain of the incident itself. For example, external communications liaison, internal communications officer, etc. The specific non-resolver responders needed depends entirely on the incident at hand. For example, an internal-facing incident has no need of an external communications liaison, while a major site degradation may require a full complement.


For more background on these and other roles, refer to PagerDuty’s [Incident Response Guide](https://response.pagerduty.com/before/different_roles/).
[block:api-header]
{
  "title": "Mobilizing a coordinated response for an existing incident"
}
[/block]
When a PagerDuty incident already exists and the decision is made that a coordinated response is needed, the Add Responders capability can be used directly from the incident - either in the web app or in the mobile app. In the web app, on the incident page, click the Add Responders button:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b2f53fc-80991663.png",
        "80991663.png",
        2234,
        1366,
        "#e2e2e1"
      ],
      "sizing": "smart"
    }
  ]
}
[/block]
In the Add Responders dialog, choose the appropriate escalation policies and individual users for the incident at hand, and optionally customize the message that will be sent to responders:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/03c75bf-77816592.png",
        "77816592.png",
        2298,
        1050,
        "#303130"
      ],
      "sizing": "smart"
    }
  ]
}
[/block]
At this point, notifications are immediately sent for each user and escalation policy selected, and each responder can independently accept or decline the request to join the response. 

For example, with the request shown in the above screenshot, there are two escalation policies being requested: Communications Liaison and Incident Commanders. If the Incident Commanders on-call immediately accepts, the request for the Communications Liaison on-call will still continue.

As well, any escalation policy included will follow its regular escalation path: if the first level responder declines or does not reply before the escalation policy’s timeout, then the second level responder on that escalation policy will be requested, and so on. Please note, however, that if the same user is on-call at multiple levels in the escalation policy, the user will only be contacted the first time the escalation reaches them.


[block:callout]
{
  "type": "info",
  "title": "Individual Users vs. Escalation Policies",
  "body": "Organizations often want to include specific employees in their coordinated response and choose the person that is most suited for the particular need. This can provide good outcomes if that individual is available for a given response but is extremely problematic if the specific individual is on vacation, sick, or otherwise unavailable. \n\nA preferable approach is to think of response team composition in terms of roles to be filled. For example, don’t plan the coordinated response with Alice, your principal datastore engineer, in mind. Instead, have an on-call rotation for engaging a datastore expert, which would be implemented in PagerDuty as an [on-call schedule](https://support.pagerduty.com/docs/schedules) placed in an [escalation policy](https://support.pagerduty.com/docs/escalation-policies). Alice and several others would all be in that rotation. \n\nThis ensures availability of datastore expertise for incidents while also distributing on-call responsibility evenly across team members. Even better is to have both a primary (level 1) and a secondary (level 2) on-call defined in the escalation policy, so that if the primary is temporarily unavailable, the secondary can respond instead.\n\nThis approach isn’t just for subject matter experts; it applies to all incident response roles: incident commander, communications liaison, support liaison, etc. You will have far more consistent incident response outcomes if you follow this practice for all such roles."
}
[/block]

[block:api-header]
{
  "title": "Directing responders to a conference bridge or chat"
}
[/block]
A key part of mobilizing a coordinated response is ensuring that all responders know where to gather for collaboration. Some organizations have a persistent conference bridge or chat room that is re-used for all major incidents, and responders already know how to connect to it. In these cases no extra effort during mobilization is required, as responders will know how to engage as soon as they receive the mobilization notification.

If the collaboration channel is different from incident to incident, or if responders are not prepared with collaboration channel details, then this information must be included in the mobilization request itself.

The simplest option is to include the information directly in your request message to responders:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bbef0cc-97735894.png",
        "97735894.png",
        1176,
        740,
        "#eeeeee"
      ],
      "sizing": "smart"
    }
  ]
}
[/block]
Alternatively, you can set up conference bridge and/or chat channel information ahead of time via Response Bridge and then include these details in the request by clicking the “Use Response Bridge” checkbox:


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9e33a80-67597744.png",
        "67597744.png",
        1152,
        942,
        "#e8e9e9"
      ]
    }
  ]
}
[/block]
With either method, responders will receive the corresponding notification on their mobile device. Both iOS and Android recognize common phone number formats, so responders can simply tap to dial the conference bridge from their SMS notification. 

This [knowledge base](https://support.pagerduty.com/docs/response-automation#section-creating-a-response-play) article has additional details on how to format phone numbers so they are correctly recognized by mobile devices.

Note that you can also include the URL for a video conference or chat channel in the responder request message, which is also tappable from SMS.
[block:api-header]
{
  "title": "One-click mobilizing of a coordinated response"
}
[/block]
Using Add Responders directly is a flexible way to choose exactly the responders needed for a given situation. However, determining which users and escalation policies to include (often by referencing written documentation to see who fits the current incident at hand), and then selecting them one by one, chews up valuable response time and is also error-prone. 

If you are frequently mobilizing the same set of responders, you can instead use [response plays](https://support.pagerduty.com/docs/response-automation) to automate and accelerate the mobilization process.

A response play lets you configure in advance the users and/or escalation policies to request as additional responders. Then, during an incident, a responder can run the appropriate play by choosing it from their list of available plays. From the PagerDuty mobile app, a play can be run on the incident like this:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4e2a3c1-Screen_Shot_2017-12-07_at_4.00.02_PM.png",
        "Screen Shot 2017-12-07 at 4.00.02 PM.png",
        608,
        357,
        "#253135"
      ],
      "sizing": "smart"
    }
  ]
}
[/block]
Running a play from the PagerDuty web app is similarly straightforward:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/513956f-98357097.png",
        "98357097.png",
        2400,
        1368,
        "#e3e3e2"
      ]
    }
  ]
}
[/block]
Immediately as the play is run, all of the additional responders identified in the play are notified, and your response team can quickly mobilize.
[block:api-header]
{
  "title": "Preparing for effective one-click mobilization"
}
[/block]
The first step in preparing for effective one-click mobilization is to plan your collaboration strategy. As mentioned earlier, the responders being mobilized must know where to gather so that they can collaborate on the incident at hand. 

If everyone that might be part of a response team knows in advance the conference bridge or chat channel that will be used for all coordinated responses, then the response play can be simple: just identify the responders needed. Otherwise, including those collaboration details directly in the response play itself will be necessary.

Here’s an example of how to include conference bridge details in a response play’s custom message to responders:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c7bb44b-1908067.png",
        "1908067.png",
        1160,
        734,
        "#414b5b"
      ],
      "sizing": "smart"
    }
  ]
}
[/block]
The next step is to identify the response teams you will be regularly assembling and create a response play for each. 

Here’s what a set of real-world response plays might look like:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3807f7e-76423351.png",
        "76423351.png",
        2198,
        694,
        "#f8f8f7"
      ],
      "sizing": "smart"
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Mobilizing automatically when an incident is created"
}
[/block]
Some scenarios require a coordinated response immediately, and ideally, mobilizing a response team happens without requiring human intervention. A few situations like this include:

* When an incident is created from business metric monitoring. e.g. revenue per hour falls below a minimum required value.
* When an incident is created from user-observable failures. e.g. website is determined to be unreachable by customers.
* When a critical incident is created based on triage that has occurred upstream of PagerDuty. e.g. an ITSM tool is in use, and only P1 incidents are synchronized with PagerDuty.

In all of these cases it is beneficial to have the response team mobilize immediately upon incident creation.

To set up response mobilization on incident creation, attach a response play to a PagerDuty service. That play will then be run on each new incident created on the service. This approach minimizes the time from incident detection until the response team is mobilized, reduces opportunities for user errors, and eliminates the perpetual need to keep the “who to page” response documentation up to date.

To attach a response play to a service, edit the service’s settings and select the desired play, as shown here:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8844c19-68226470.png",
        "68226470.png",
        1608,
        864,
        "#353637"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Adding responders to an ongoing response"
}
[/block]
Especially for complex or long-running incidents, it’s often necessary to add responders to an ongoing effort. In somes cases, the scope increases and additional subject-matter experts are needed. In other cases, it’s necessary to rotate in fresh responders to take over for flagging participants that have been engaged for hours. The already-discussed mobilization techniques can be used for both of these situations, with a few new considerations.

Using a response play to bring in new subject-matter experts mid-incident can be very effective, but the shape of this response play will differ from plays that mobilize an entire coordinated response. An SME play will reference a set of subject-matter expert escalation policies but skip the other coordinated response roles: incident commander, customer support liaison, etc. One such SME play might bring in infrastructure and SRE on-calls: network, platform, and security. This would be useful if an incident at first seemed like an application-level issue but was subsequently determined to involve lower layers of the technology stack.

When rotating fresh responders into a response, a completely different approach is needed. It is very difficult to use a response play for this, as the situation is more ad hoc and harder to plan for. Also, while the Add Responders functionality can be used, using an escalation policy is often not effective because the primary responder for that policy is likely the participant you’re looking to replace!

In this case, the best approach requires more direct involvement by the incident commander:

* Examine the appropriate escalation policy for the role/expertise you’re looking to rotate responders for.
* Find the responder that would be next up if the current responder wasn’t already involved.
* Use Add Responders to request that specific responder as an individual. When sending the request, it can be helpful to customize the notification request to mention that they are being requested to rotate out an existing responder.

[block:api-header]
{
  "title": "Summary"
}
[/block]
Using features like [Response Plays](https://support.pagerduty.com/docs/response-automation) and [Response Mobilizer](/docs/mobilizing-a-response#section-add-responders-to-an-incident) on the PagerDuty platform, you can proactively prepare for incidents and set up your coordinated response team for success. For a detailed overview on establishing best practices, as well as more examples on how you can leverage PagerDuty’s capabilities, please refer to our [Incident Response Guide](http://response.pagerduty.com/). 

We also recommend reviewing the following how-to guides, which cover additional major incident response topics:

* [Communicate Effectively with Stakeholders](https://support.pagerduty.com/docs/how-to-effective-stakeholder-communications)
* [Triage Major Incidents & Integrate Your ITSM Toolchain](https://support.pagerduty.com/docs/how-to-triaging-major-incidents-integrating-your-itsm-toolchain)