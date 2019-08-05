---
title: "Quick Start Guide"
excerpt: ""
---
This article will help you get started with your new PagerDuty account. If there are any terms that are unfamiliar you may want to check out our [Glossary of Terms](doc:glossary).
[block:api-header]
{
  "title": "Create a User Profile"
}
[/block]
To open your profile page, click your avatar in the upper right corner and click **My Profile**. On your profile page, there are three tabs for configuring your settings.

## Contact Information

The **Contact Information** tab is where you add contact methods, as well as view recent incident activity. Add contact methods on this page — refer to the [push notification guide](doc:mobile-app#section-adding-a-mobile-device-for-push-notifications) to add your mobile device.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f758c66-QuickStarGuide_CoreConcepts_img1.png",
        "QuickStarGuide_CoreConcepts_img1.png",
        1017,
        1062,
        "#f4f4f3"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "You can add a maximum of 10 contact methods, regardless of type."
}
[/block]
## Notification Rules

Notification rules define how and when you are notified when an incident is assigned to you. Notification rules for high- and low-urgency incidents are configured separately. You can also receive notifications when you are going on- or off-call.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cb868f4-QuickStartGuide_CoreConcepts_img2.png",
        "QuickStartGuide_CoreConcepts_img2.png",
        1018,
        912,
        "#374c56"
      ]
    }
  ]
}
[/block]
You can stagger notifications by entering an amount of time after an incident triggers.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9830e3b-QuickStartGuide_CoreConcepts_img3.png",
        "QuickStartGuide_CoreConcepts_img3.png",
        1011,
        214,
        "#343d4d"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Tip",
  "body": "We recommend that you set your notification rules to contact you shortly after an incident is triggered. A minimum of 2 notification rules will help make sure you do not miss a critical notification."
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "You can create up 20 high-urgency and 10 low-urgency notification rules."
}
[/block]
[See our best practice tips around setting up notification rules](https://community.pagerduty.com/t/notifications-setting-up-notification-rules/452)

## User Settings

The **User Settings** tab is where you can:
- update your login email and password.
- add your Gravatar photo.
- change the color to represent your schedule shifts.
- revoke access to linked applications.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/870f65b-QuickStartGuide_CoreConcepts_img4.png",
        "QuickStartGuide_CoreConcepts_img4.png",
        1015,
        592,
        "#dddcdd"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Create an On-call Schedule"
}
[/block]
On-call schedules allow you to create rotations so that users are only notified when they should be. Schedules are available on Platform Team, Platform Business, and Enterprise.

You can create a schedule under **Configuration** → **Schedules** → **New On-Call Schedule**. Add users to the shift (schedule layer), select how frequently the shift rotates, and at what time the shift is handed off to the next user.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0d7a225-QuickStartGuide_CoreConcepts_img5.png",
        "QuickStartGuide_CoreConcepts_img5.png",
        1018,
        753,
        "#2b5d74"
      ]
    }
  ]
}
[/block]
For more details on schedule configuration:

* [Best practice tips: Effective start and end scheduling](https://community.pagerduty.com/t/scheduling-effective-start-end-practices-for-on-call-scheduling/474)

* [Resources around setting up on-call schedules](doc:schedules)

* [On-call schedule examples](doc:schedule-examples)
[block:api-header]
{
  "title": "Create an Escalation Policy"
}
[/block]
Escalation policies determine who should be assigned to an incident and what should happen to that incident when there is no response.

These can be made under **Configuration** → **Escalation Policies** → **New Escalation Policy**. You can add users or schedules to the levels of your policy. If an incident is not ack'ed or resolved within the [acknowledgement timeout period](/docs/service-settings#section-acknowledgement-timeouts), it will escalate to the next level. You can also set how many times you'd like an escalation policy to repeat.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d17840a-epex.png",
        "epex.png",
        987,
        913,
        "#eff0f0"
      ]
    }
  ]
}
[/block]
[Find more info about  escalation here](doc:escalation-policies)
[block:api-header]
{
  "title": "Create Teams"
}
[/block]
Teams allow you to organize and filter views in the mobile and web app. This feature is available on the Platform Business and Enterprise plans.

You can create a team under **Configuration** → **Teams** → **New Team**. Associate the Team with an escalation policy, and it'll automatically associate it with relevant users, schedules, and services. You can manually add or remove users, too, at any time.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1397ef3-create_team.png",
        "create_team.png",
        932,
        294,
        "#314b49"
      ]
    }
  ]
}
[/block]
[Learn more about Teams](doc:teams)
[block:api-header]
{
  "title": "Create a Service"
}
[/block]
Services represent an area of your application. You can have one or more integrations on a service. Each service is associated with a single escalation policy. 

1. Go to **Configuration** → **Services** → **Add New Service**.

2. Give the service any name, and choose an integration type when prompted.

3. Choose an escalation policy to use for this service, and customize other incident settings as needed.

4. Follow the [instructions to set up the integration](https://www.pagerduty.com/integrations). If the monitoring tool you are using does not appear on the list, you can follow the [generic email integration guide](https://www.pagerduty.com/docs/guides/email-integration-guide/). Alternatively, you can select **Use our API directly**. If your service is able to make basic HTTP API calls, then you can interact directly with our API to trigger, acknowledge, and resolve incidents. Our [developer documentation](https://developer.pagerduty.com/docs/events-api) provides several examples of how to integrate with PagerDuty using our API.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bf7c97b-New_Service_-_PagerDuty.png",
        "New_Service_-_PagerDuty.png",
        990,
        1212,
        "#405965"
      ]
    }
  ]
}
[/block]
On a service's **Integrations** tab, click **New Integration** to add more integrations. 

To test the settings you have created in your new PagerDuty account, you can trigger an incident using our guide: [Triggering an Incident with Web UI, Email, or API](/docs/alerts-and-incidents#section-triggering-an-incident-with-web-ui-email-or-api).