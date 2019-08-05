---
title: "Notification Content and Behavior"
excerpt: ""
---
[block:api-header]
{
  "title": "Information that is Included in Notifications"
}
[/block]
A notification is sent to the user currently on-call when an incident is triggered. PagerDuty sends out notifications via the following channels:
- [Email Notifications](#section-email-notifications)
- [SMS Notifications](#section-sms-notifications)
- [Phone Notifications](#section-phone-notifications)
- [Push Notifications](#section-push-notifications)

Each of these channels will display different information about an incident that is assigned to you.

##Email Notifications
###What address will emails be sent from?
PagerDuty email notifications are sent from `no-reply@pagerduty.com`.

###What will the subject line contain?
PagerDuty email notifications will be sent with a subject line similar to the following:
`[PagerDuty Alert] You have 1 TRIGGERED Incidents (4cb96)`

If multiple incidents are assigned to you, PagerDuty will bundle all incidents into one email and you will receive a subject line similar to the following:
`[PagerDuty Alert] You have 3 TRIGGERED Incidents (db97d)`

[Find out more about notification bundling…](#section-notification-bundling)

###What will be included in email notification?

- The incident number
- Trigger date and time
- The service name
- The email subject (this will be the same as the **Title** field in an incident)
- Link to the incident in PagerDuty
- The escalation policy associated with the service
- The email body (This will be the same as the **Details** field in an incident)

###Can I enable or disable rich-text / HTML email notifications?
Yes. For each email address you have configured within your Contact Information, you can choose to receive HTML emails. If this option is unselected, basic text email notifications will be sent.

Here is an example of a PagerDuty text-only email notification:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a103288-PagerDuty_Email_Alert.png",
        "PagerDuty Email Alert.png",
        490,
        410,
        "#21406e"
      ]
    }
  ]
}
[/block]
Here is an example of a PagerDuty HTML email notification:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f6e5c8b-WhatinfoisinNotifications-emailwithHTML.png",
        "WhatinfoisinNotifications-emailwithHTML.png",
        584,
        806,
        "#ece8e7"
      ]
    }
  ]
}
[/block]
When you receive a PagerDuty email notification, the "Details" section of each incident will be truncated to 500 characters. You can include clickable links in this truncated message. The rest of the email body can be accessed in PagerDuty within the incident logs and details or via the [mobile app](/docs/mobile-app#section-mobile-app-walkthrough).

Attachments are stripped from PagerDuty email notifications and also from the incident logs. To view the original attachment, you will want to refer to the system that sent out the original attachment.

##SMS Notifications
###What number will SMS notifications be sent from?
Any PagerDuty SMS notifications sent to a US phone number will be sent from **PDUTY (738-89)** and any failover will be sent via any of [these numbers](doc:notification-phone-numbers#section-phone-numbers-notifications-are-sent-from). Standard text messaging rates should apply to all PagerDuty SMS notifications.

If you are outside the US, refer to [this list of numbers](doc:notification-phone-numbers).

###What will be included in SMS notification?
An incident triggered from an [Email Integration Service](https://www.pagerduty.com/docs/guides/email-integration-guide/) will contain the following information in a PagerDuty SMS notification:
- The incident number
- The name of the PagerDuty service (in our example it is "Shopping Cart")
- The description of the incident (equivalent to the subject line of the triggered incident, in this example it is "Test Incident")
- Codes to ack and resolve

All PagerDuty SMS notifications are truncated to meet the 160 character limit for text messages.

Here is an example of a PagerDuty SMS notification:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7aa72ab-notification-content-sms.jpg",
        "notification-content-sms.jpg",
        552,
        186,
        "#dedee2"
      ]
    }
  ]
}
[/block]
If multiple incidents are assigned to you, then PagerDuty will bundle all notifications into 1 SMS notification, listing out the incident numbers and giving you the option to only ack all or resolve all incidents at once.

##Phone Notifications
###What number will phone notifications come from?

Check out our [PagerDuty Phone Call Notifications guide](https://support.pagerduty.com/docs/notification-phone-numbers#section-pagerduty-phone-call-notifications) to learn more.

###What will be included in a phone call notification?
An incident triggered from an Email Integration Service will contain the following information in a PagerDuty phone call notification:
- Name of the affected PagerDuty service
- Description of the incident (subject line of the incident)
- Options to ack, resolve, escalate

Here is an example of what you will hear in a PagerDuty phone notification:
>You have "*Number*" triggered incidents on "*Service Name*". Failure is "*Email Subject*". Press 4 to Acknowledge, 6 to Resolve, or 8 to Escalate.

##Push Notifications
###What will be included in push notifications?
A notification triggered from an [Email Integration Service](https://www.pagerduty.com/docs/guides/email-integration-guide/) will contain the following information in a PagerDuty push notification:
- Incident number
- Name of the affected PagerDuty service
- Description of the incident (subject line of the incident)

Here is an example of a PagerDuty push notification:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6c43cee-IMG_4579_2.png",
        "IMG_4579_2.png",
        750,
        667,
        "#1c2835"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Notification Bundling"
}
[/block]
"Notification bundling" is PagerDuty's term for the incident summary we switch to when multiple incidents are triggered and assigned to a user.

PagerDuty's mission is to notify you to the incidents you need to know about, at the level you need to know them. This directive becomes complicated when your notification volume explodes: if 100 notifications a minute are incoming, what is the best way to notify you?

Normally, we would notify you for each individual incident. However, if your notification method is set to phone, and your phone starts ringing off the hook until 100 consecutive phone calls and voicemails are pushed through, the problem becomes serious. We call these "notification storms," and calibrate our policies to avoid this.

Notification bundling means we roll together or bundle these multiple notifications into a single summarizing notification, regardless of your notification method (phone, SMS, email, or push). All incidents that are in the triggered state (i.e. not acknowledged or resolved) will be included in the bundled notification.

Here are examples of how each contact method will notify you, in the event of near-simultaneous incidents. For this example, assume I've triggered 5 incidents on a service named "Nagios" within a 1-minute time frame.

##Phone
`You have 5 triggered incidents on Nagios. Press 4 to acknowledge all incidents. Press 6 to resolve all incidents. Press 0 for help or press * to repeat this message.`

##SMS
`ALRT: #100,#101,#102,#103,#104 on Nagios. Reply 14:Ack all, 16:Resolv all`

##Email
```
You are assigned 5 triggered incidents in PagerDuty:
Please visit the following URL to manage these incidents.
https://fake-name.pagerduty.com/dashboard

1) Incident #100
   Opened on: Jan 1 at 12:00pm PST
   Service: Nagios
   Description: Emergency in the server room
   Link: https://fake-service.pagerduty.com/i/100
```
Another way to minimize the number of notifications that you receive is to adjust your notification rules so that you are notified of an incident several minutes after it is assigned to you as opposed to immediately after it is assigned to you. Adjusting the notification rules will allow more time for incidents to aggregate and you will receive fewer notifications during a notification storm.
[block:api-header]
{
  "title": "Responding to SMS and Phone Notifications"
}
[/block]
##Responding to an SMS Notification

To reply to an SMS notification you will reply with the unique code that is provided. Here is an example:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2e67196-ack_screenshot.jpg",
        "ack_screenshot.jpg",
        750,
        1334,
        "#e9e7ed"
      ]
    }
  ]
}
[/block]
##Responding to a Phone Notification
Please respond to a phone notification by pressing:
4. Acknowledge
6. Resolve
8. Escalate — if there is another level in your escalation policy

##Responding from the Mobile Site or the App
See [Responding to Incidents in the Mobile App](/docs/mobile-app#section-responding-to-incidents-in-the-mobile-app).

##Responding to an Email Notification
At this time it is not possible to acknowledge or resolve an incident via email. To take action for the open incident you must use the PagerDuty site or mobile app, or respond via an SMS notification or phone call you receive as described below.