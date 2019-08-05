---
title: "Response Plays"
excerpt: ""
---
[block:callout]
{
  "type": "info",
  "body": "Response Plays are available on our **Enterprise** plan and as part of our [Modern Incident Response](https://support.pagerduty.com/docs/pagerduty-modern-incident-response) package. Please [contact our Sales Team](https://www.pagerduty.com/contact-sales/) if you would like to upgrade to a plan with this feature.",
  "title": ""
}
[/block]

[block:api-header]
{
  "title": "What Is A Response Play?"
}
[/block]
Response plays let you create packages of incident actions that can be applied at any time to an incident with just a single button click, that can be immediately applied to all new incidents created on a service, or that can be automatically applied to an incident [disrupting a business service](https://support.pagerduty.com/docs/business-services#section-creating-business-services). This enables you to take a complex activity, like assembling a response team of multiple on-calls and an incident commander, and make it available to anyone that needs to use it. Grouping up these actions into a reusable play has several benefits:

  * Turn documented processes into executable objects.
  * Reduce the opportunity for errors and mistakes while following incident response processes.
  * Drastically cut down on the time taken to execute incident response processes.  
[block:api-header]
{
  "title": "What Can A Response Play Do?"
}
[/block]
The current set of actions that can be a part of a response play include:

* **Mobilize a Response** (Notify responders other than the assignee to help resolve the incident.)
* **Engage Stakeholders** (Subscribe people who are not directly involved with resolving the incident to receive **status updates**.)
* **Publish Status Updates** (Send a prepared status update to all subscribers attached to the incident, to keep them aware of the incident’s progress.)
* **Add a Response Bridge** (View the response bridge details on the incident details page.)
[block:api-header]
{
  "title": "Example Usage"
}
[/block]
A response play can be used directly by on-call engineers during triage when they determine something they’ve been paged for is bigger than expected. A service can also be configured to run a response play automatically whenever an incident opens on that service.
[block:api-header]
{
  "title": "Creating A Response Play"
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "Required User Permissions",
  "body": "Manager, Global Admin or Account Owner base roles can create response plays.\n\nTo check what role you have, or if you need your permissions adjusted, please visit our section on [Changing User Roles](https://support.pagerduty.com/docs/user-roles#section-changing-user-roles)."
}
[/block]
You can create a new response play by going to **Configuration** :fa-arrow-right: **Response Plays**. You can now create a new response play by clicking on the **New Response Play** button. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2b64f5f-create_response_play.png",
        "create_response_play.png",
        1957,
        964,
        "#1f3440"
      ],
      "border": false,
      "sizing": "smart"
    }
  ]
}
[/block]
You can also view/edit/delete any of your previously created response plays.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/69f480a-Screen_Shot_2017-09-05_at_9.39.07_PM.png",
        "Screen Shot 2017-09-05 at 9.39.07 PM.png",
        3292,
        602,
        "#f7f7f7"
      ],
      "border": false,
      "sizing": "smart"
    }
  ]
}
[/block]
###Custom Response Message

You may also want to use a custom responder message - this allows you to specify a conference bridge or Slack channel where the response will be taking place.

You can add phone numbers and/or URLs in the message to responders. Here’s how:

Under the **Notify responders…** option, select **Send a custom message to responders**. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5f5ec1e-custom_msg.png",
        "custom_msg.png",
        1976,
        1705,
        "#e7e7e3"
      ],
      "border": false,
      "sizing": "smart"
    }
  ]
}
[/block]
Phone numbers should be formatted like 234-567-8912,,,,1234#, where a comma (,) represents a one-second wait and pound (#) completes access code input.

Responders will be able to tap on the phone number and/or video call URL directly from the SMS they receive.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dde6ba9-Screen_Shot_2017-11-29_at_12.17.48_PM.png",
        "Screen Shot 2017-11-29 at 12.17.48 PM.png",
        818,
        1440,
        "#eb1e24"
      ],
      "sizing": "smart",
      "border": false
    }
  ]
}
[/block]
Here are phone number formats that will work:

+1-234-567-8912
+1(234) 567-8912
+1 (234) 567-8912
(234) 567-8912
234.567.8912
234-567-8912
1-234-567-8912
1 (234) 567-8912

###Automatically add a response bridge

You can automatically include meeting details for a response bridge in the incident details. This will make the meeting details available to responders looking at the incident in the mobile app or in the web app. Note: to send meeting details in the request to responders itself, you must also include it directly in the custom message to responders.

Select the **Share conference bridge information with responders** option to enter the meeting details: 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6b6cd45-response-plays-add-conference-bridge.png",
        "response-plays-add-conference-bridge.png",
        2074,
        1800,
        "#ededee"
      ]
    }
  ]
}
[/block]
###Managing who can run this play on demand

You have the option of associating a response play to a team. At the moment only one team can be assigned to a response play. The team determines when the play will be shown in the Run a Play listing dropdown. 

In the visibility setting, you have the following options:
  * *No one can run this play on demand*: This ensures that the play will not be suggested to responders when looking at an incident. This is useful for plays attached to services that automatically trigger incidents.
  * *All incident responders*: This play will be shown to all responders, regardless of what team they are on.
  * *Incident responders on a specific team* (only available if the play is associated with a team): The play will be shown on an incident's Run a Play listing, but only when the active user is a member of the play's team. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/edd7319-response-play-teams-kb-article.png",
        "response-play-teams-kb-article.png",
        2042,
        2218,
        "#f9f9f8"
      ],
      "sizing": "smart",
      "border": false
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Running A Response Play On An Incident"
}
[/block]
From the Incident details page, you can **Run a Play** from the button bar of the incident. You can select any play from the list.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/08210ee-Screen_Shot_2017-09-05_at_10.10.54_PM.png",
        "Screen Shot 2017-09-05 at 10.10.54 PM.png",
        1166,
        546,
        "#2d5d32"
      ],
      "border": false
    }
  ]
}
[/block]
A confirmation box will pop up to confirm your selection for running the play. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/89b40b6-Screen_Shot_2017-10-27_at_3.41.48_PM.png",
        "Screen Shot 2017-10-27 at 3.41.48 PM.png",
        1208,
        460,
        "#323232"
      ],
      "border": false,
      "sizing": "smart"
    }
  ]
}
[/block]
If you added responders to a play, your responders will have the ability to **Accept** or **Decline** your request.
[block:api-header]
{
  "title": "Automatically Running A Response Play At Incident Creation"
}
[/block]
You can run a response play whenever an incident is created on a service. Choose the service and click :fa-edit: **Edit Service**. Once on the edit screen, you can choose or clear the response play that will be used for new incidents on the chosen service.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/84f4ae8-Screen_Shot_2017-10-27_at_11.33.00_AM.png",
        "Screen Shot 2017-10-27 at 11.33.00 AM.png",
        1608,
        864,
        "#dbe0e4"
      ],
      "border": false,
      "sizing": "smart"
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Running A Play From The Mobile App"
}
[/block]
You can download the app from the [App Store](https://itunes.apple.com/us/app/pagerduty/id594039512) for iOS or [Google Play](https://play.google.com/store/apps/details?id=com.pagerduty.android) for Android. Screenshots are from our iOS app, and the Android app is very similar.

Open an incident and click **More**
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f0efe74-mobile_1.jpeg",
        "mobile_1.jpeg",
        750,
        1334,
        "#212836"
      ],
      "sizing": "smart",
      "border": false
    }
  ]
}
[/block]
Tap **Run a Play**
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/eff1113-mobile_2.jpeg",
        "mobile_2.jpeg",
        750,
        1334,
        "#f7f1f8"
      ],
      "border": false,
      "sizing": "smart"
    }
  ]
}
[/block]
Confirm that you want to Run the play
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5afcb35-step_3.jpg",
        "step_3.jpg",
        750,
        1334,
        "#131b23"
      ],
      "border": false,
      "sizing": "smart"
    }
  ]
}
[/block]