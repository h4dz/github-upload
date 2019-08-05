---
title: "Conference Bridge"
excerpt: ""
---
[block:callout]
{
  "type": "info",
  "body": "This feature is available to customers on our Enterprise plan and as part of the [Modern Incident Response](https://support.pagerduty.com/docs/pagerduty-modern-incident-response) package. Please contact our [Sales Team](https://www.pagerduty.com/contact-sales/) if you would like to upgrade to a plan featuring Conference Bridge.",
  "title": "Note"
}
[/block]
A conference bridge allows you to use your preferred web conferencing provider for incident responders. There are four ways to add a conference bridge:
- [Account-level Conference Bridge](#section-account-level-conference-bridge)
- [Service-level Conference Bridge](#section-service-level-conference-bridge)
- [Manually Add a Conference Bridge to an Incident via Response Mobilizer](#section-manually-add-a-conference-bridge-to-an-incident-via-response-mobilizer)
- [Automatically with a Response Play](/docs/response-automation#section-automatically-add-a-conference-bridge)

#Account-level Conference Bridge
Conference bridges can be added as account-level extensions. This provides users with a list of persistent conference lines to choose from when triggering an incident.
1. Go to **Configuration → Extensions**.
2. Go to the **Conference Bridges** tab, and click **New Conference Bridge**.
3. Add a **Label**, **Description**, **Conference Number**, and **Conference URL** for your conference bridge, and click **Save**.
    - The **Label** is the name of the conference bridge as it will appear in the selection drop-down menu.
    - The **Description** is a brief explanation of the conference bridge.
    - The **Conference Number** is the phone number users will call into. Phone numbers should be formatted like `415-555-1212,,,,1234#`, where a comma (`,`) represents a one-second wait and pound (`#`) completes access code input.
    - The **Conference URL** is the meeting URL for screen sharing purposes.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c9c5234-conference-bridge-extensions-page.png",
        "conference-bridge-extensions-page.png",
        2394,
        1082,
        "#f4f3f2"
      ]
    }
  ]
}
[/block]
4. Now the conference bridge will be available as an option when adding a bridge to an incident.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f4f1ffe-cb_manual_incident.png",
        "cb_manual_incident.png",
        696,
        842,
        "#459d14"
      ]
    }
  ]
}
[/block]
#Service-level Conference Bridge
When adding a conference bridge to a service it is important to note that the conference bridge information will appear on **all incidents that trigger on that service**. We recommend adding a conference bridge to services dedicated to critical incidents that require a bridge.
1. Go to **Configuration → Services**.
2. Find your service and click **Edit Service** from the right sidebar.
3. While in edit mode, go to **Conference Bridge Settings** section — this is where you can add the conference bridge information for your service.
    - Phone numbers should be formatted like `415-555-1212,,,,1234#`, where a comma (`,`) represents a one-second wait and pound (`#`) completes access code input.
    - You can also enter an optional **Meeting URL**.
4. When you are done, click **Save changes**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b44b8c4-cb_add_to_service.png",
        "cb_add_to_service.png",
        1253,
        305,
        "#424856"
      ]
    }
  ]
}
[/block]
When an incident is triggered on your service you will see the conference bridge information in the web UI, email notifications, and Slack (if you have a [Slack integration](https://www.pagerduty.com/docs/guides/slack-integration-guide/) configured).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4cb4039-cb_incident_detail.png",
        "cb_incident_detail.png",
        556,
        371,
        "#ceeed2"
      ]
    }
  ]
}
[/block]
#Manually Add a Conference Bridge to an Incident via Response Mobilizer
If you do not have conference bridge information added to your service, you can use the **Add Responders** feature to input the conference bridge information.
1. After an incident has been triggered, acknowledge the incident and click on **Add Responders** at the top right-hand corner.
2. Select the users/escalation policies you wish to add as a responder. 
3. You can also add a note to send to the users you are requesting to join as a responder.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c2c9e54-cb_add_responder.png",
        "cb_add_responder.png",
        835,
        673,
        "#449f13"
      ]
    }
  ]
}
[/block]
4. To add in your conference bridge details:
    - Phone numbers should be formatted like `415-555-1212,,,,1234#`, where a comma (`,`) represents a one-second wait and pound (`#`) completes access code input. 
    - You can also enter an optional **Meeting URL**.
5. Click **Add Responder**.

Requests will be sent to responders, who can review conference bridge details on the incident details page and in the responder email notifications.

At this time, if you wish to add a conference bridge to an open incident you will need to use the add responders feature. On the other hand, if you've configured a service-level conference bridge, you can enter new conference bridge info when adding a bridge via Response Mobilizer.

#Add a Conference Bridge via a Response Play
Adding a conference bridge to a response play allows you to easily mobilize your responders - you can do this automatically at the service level or for individual incidents. 
1. Go to **Configuration** → **Response Plays**.
2. Select **New Response Play**.
3. Add responders to notify when the response play is run.
4. Configure the conference bridge information - this will be shared with responders when the response play is run.
5. When you are done, click **Save changes**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5c66f89-Screen_Shot_2018-10-18_at_9.30.14_AM.png",
        "Screen Shot 2018-10-18 at 9.30.14 AM.png",
        937,
        373,
        "#fafafa"
      ]
    }
  ]
}
[/block]
Once you've created the response play, you can configure the play to run automatically at the service level for all incidents that are created on that service. You can also allow your responders to run the response play on demand. This will allow them to run Response Plays for individual incidents. You can learn more about response plays [here](https://support.pagerduty.com/docs/response-automation).

#Joining Conference Bridges as a Responder

Conference bridge information is available within incidents in the web UI, email notifications, Slack (if you have a [Slack integration](https://www.pagerduty.com/docs/guides/slack-integration-guide/) configured) and via voice call. When referencing the web UI, email notifications and Slack, responders will need to manually dial into the conference bridge or click its link. For voice call notifications, responders have the option of using the [One Touch To Join](https://support.pagerduty.com/docs/conference-bridge#section-one-touch-to-join-conference-bridge) feature. 

##Conference Bridge Information in the Web UI
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/73df63d-conference-bridge-info-incident.png",
        "conference-bridge-info-incident.png",
        1600,
        790,
        "#f3f2f2"
      ]
    }
  ]
}
[/block]
##Conference Bridge Information in Email Notifications
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fa63160-conference-bridge-info-email.png",
        "conference-bridge-info-email.png",
        1210,
        1208,
        "#f8f5f5"
      ]
    }
  ]
}
[/block]
##Conference Bridge Information in Slack Notifications
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7b2f42f-conference-bridge-info-slack.png",
        "conference-bridge-info-slack.png",
        1030,
        328,
        "#f2f0f2"
      ]
    }
  ]
}
[/block]
##Conference Bridge Information in Voice Call Notifications

When responders receive voice call notifications, they will hear the following prompt:

"*PagerDuty Alert.  Please help me with [Incident Title]*

*Press 1 to accept the request*
*Press 2 to decline the request*"

**By default, they will not be able to receive conference bridge information in the voice call**. Once accepted, they will then need to check the incident in the [web UI](https://support.pagerduty.com/docs/conference-bridge#section-conference-bridge-information-in-the-web-ui), an [email notification](https://support.pagerduty.com/docs/conference-bridge#section-conference-bridge-information-in-email-notifications) or a [Slack notification](https://support.pagerduty.com/docs/conference-bridge#section-conference-bridge-information-in-slack-notifications) to obtain the conference bridge information and enter the bridge manually. 

**If you would like responders to be able to join conference bridges via voice call notifications**, you can opt to use our [One Touch To Join Conference Bridge](https://support.pagerduty.com/docs/conference-bridge#section-one-touch-to-join-conference-bridge) add-on feature.

##One Touch To Join Conference Bridge
[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "One Touch to Join Conference Bridge works with the [Conference Bridge](https://support.pagerduty.com/docs/response-bridge#section-service-level-response-bridge) and [Add Responders](https://support.pagerduty.com/docs/mobilizing-a-response#section-add-responders) capabilities available in our [Modern Incident Response](https://support.pagerduty.com/docs/pagerduty-modern-incident-response) product add-on. It can be enabled upon request for customers with [Modern Incident Response](https://support.pagerduty.com/docs/pagerduty-modern-incident-response) - please reach out to your sales representative for more information."
}
[/block]
The One Touch To Join Conference Bridge feature enables rapid response team assembly by giving responders a push-button means of joining a conference bridge. This feature relies on two existing [Modern Incident Response](https://support.pagerduty.com/docs/pagerduty-modern-incident-response) features: [Conference Bridge](https://support.pagerduty.com/docs/response-bridge#section-service-level-response-bridge) and [Add Responders](https://support.pagerduty.com/docs/mobilizing-a-response#section-add-responders). When responders are added to an incident and receive a voice call, they will receive the option to “Join the bridge” which will immediately add them to the conference call. The One Touch To Join Conference Bridge solution works with your existing direct-dial conference bridge provider and reduces effective time-to-engage and resolution time for major incidents.

Configure One Touch To Join Conference Bridge:

1. [Configure a conference bridge](https://support.pagerduty.com/docs/response-bridge).
2. Responders must have:
    a. A phone number listed in the **Contact Information** tab of their PagerDuty user profile.
    b. A high-urgency notification rule in the **Notification Rules** tab using this phone number in their user profile.



[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/28ac901-one-touch-responder-phone.png",
        "one-touch-responder-phone.png",
        1370,
        720,
        "#f8f7f7"
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
        "https://files.readme.io/a16f561-one-touch-high-urgency-notification-rule.png",
        "one-touch-high-urgency-notification-rule.png",
        1138,
        218,
        "#e7e0df"
      ]
    }
  ]
}
[/block]
3. During an incident with a conference bridge, add responders by using the [Add Responders](https://support.pagerduty.com/docs/mobilizing-a-response#section-add-responders) feature or at-scale with [Response Plays](https://support.pagerduty.com/docs/response-automation). 

Any requested responder with the above configuration will receive a voice call with the following phrasing:

"*PagerDuty Alert.  Please help me with [Incident Title]*

*Press 1 to join the bridge*
*Press 2 to accept the request*
*Press 3 to decline the request*"

The following table lists the effects of each response to the voice call:
[block:parameters]
{
  "data": {
    "h-0": "Response to Voice Call",
    "h-1": "Result",
    "h-2": "Responder Status",
    "h-3": "Conference Bridge Impact",
    "h-4": "Incident Timeline",
    "0-0": "1 - Join the Bridge",
    "1-0": "2 - Accept the Request",
    "2-0": "3 - Decline the Request",
    "3-0": "No Answer",
    "0-1": "Responder joins the bridge and Responder Request is accepted.",
    "1-1": "Responder Request is accepted.",
    "2-1": "Responder Request is declined.",
    "3-1": "Responder Request is unanswered.",
    "0-2": "Responder Status is marked as **Engaged**, as per the [icon on the Responders box in the Incident Detail page](https://support.pagerduty.com/docs/mobilizing-a-response#section-status-of-responders).",
    "1-2": "Responder Status is marked as **Engaged**.",
    "2-2": "Responder Status marked as **Declined**.  \n\nIf the Added Responder is part of an Escalation Policy (EP) the responder on the next EP level would be paged with an Add Responder request.",
    "3-2": "Responder Status remains marked as **Pending**.  \n\nIf the Added Responder is part an Escalation Policy (EP) the responder on the next EP level would be paged with an Add Responder request.",
    "0-3": "Responder automatically joins to the bridge for the incident.  No manual dialing required.",
    "1-3": "The responder will have to manually dial into the bridge and their participation will not be visible on the Timeline.",
    "2-3": "None",
    "3-3": "None",
    "0-4": "An Incident Timeline entry is created showing when the Responder joined the call.",
    "1-4": "An Incident Timeline entry is created showing this accepted request.",
    "2-4": "An Incident Timeline entry is created showing this declined  request.",
    "3-4": "None"
  },
  "cols": 5,
  "rows": 4
}
[/block]
Whenever a responder who has joined the bridge via One Touch To Join disconnects or the overall bridge call ends, the Incident Timeline will reflect these departures as well. This information can then be used in incident analysis using the [Postmortems](https://support.pagerduty.com/docs/postmortems) tool.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/946be0f-one-touch-timeline-view.png",
        "one-touch-timeline-view.png",
        1408,
        342,
        "#eff0f1"
      ]
    }
  ]
}
[/block]
You can add as many responders to your conference bridge as your conference provider allows.  One Touch To Join calls will disconnect after **two hours**.  Should the responder still need to participate, they can manually redial the bridge based on the conference details attached to the PagerDuty incident.

If a responder misses a voice call, PagerDuty will attempt to reach them using each of the configured contact methods used by their high-urgency notification rules. We recommend that at least two contact methods are configured so that if a notification for one channel is missed, context is provided in the other channel. Thus, is the voice call is missed, the responder will still be able to manually join the conference bridge using information found in the web UI, email notification or Slack message, but they will not be able to use One Touch To Join. 

####Supported Countries and Pricing

The One Touch To Join feature is supported in over 30 of our highest responder countries.  We’ve classified countries into two groups: Base or Premium (listed in table below). The One Touch To Join feature is available when:

- The conference bridge is hosted in a Base country, and
- The phone numbers of requested responders are for Base or Premium locales.

There is a telephony cost to PagerDuty when connecting One Touch To Join responders to a conference bridge.  PagerDuty will bill this cost, using the Base and Premium definition described above, based on the customer’s usage. For details on One Touch To Join pricing, please visit the [FAQ section of our Pricing page](https://www.pagerduty.com/pricing/).
[block:parameters]
{
  "data": {
    "0-0": "Canada\nChina\nIndia\nMexico\nUnited Kingdom\nUnited States",
    "h-0": "Base Rate Countries",
    "h-1": "Premium Rate Countries*",
    "0-1": "Argentina\nAustralia\nBrazil\nBulgaria\nCosta Rica\nCzech Rep.\nFrance\nGermany\nGuatemala\nHungary\nIndonesia\nIreland\nIsrael\nJapan\nNetherlands\nNew Zealand\nNigeria\nPakistan\nPhilippines\nPoland \nRussia\nSingapore\nSouth Africa\nSpain\nSri Lanka\nTaiwan\nUkraine"
  },
  "cols": 2,
  "rows": 1
}
[/block]
*One Touch To Join works with conference bridges hosted in Base Rate countries only.