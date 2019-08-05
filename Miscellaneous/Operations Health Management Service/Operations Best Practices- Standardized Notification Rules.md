---
title: "Operations Best Practices: Standardized Notification Rules"
excerpt: ""
---
#Problem Statement

Notifying responders on all channels simultaneously creates alert fatigue and negatively impacts Operations Health.

#Best Practices

##High-Urgency Incidents

We recommend using the 0-2-5 minute notification sequencing approach for high urgency incidents to reduce alert noise and ensure alerts are not missed or escalated unnecessarily. These settings are changed on an individual user basis and should be set as a policy across the organization, as appropriate, through a well-communicated process.  

1. Click the **Profile Icon** in the upper right-hand corner of your PagerDuty dashboard and select **My Profile**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b40689f-OHMS-SN-My-Profile.png",
        "OHMS-SN-My-Profile.png",
        488,
        368,
        "#bec0c5"
      ]
    }
  ]
}
[/block]
2. Select the **Notification Rules** tab and adjust the rules under **When a high-urgency incident is assigned to me**. The rules should be set so that you are notified with a push notification at zero minutes, an SMS at two minutes and a phone call at five minutes after a high-urgency incident is assigned.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b8d3c3e-OHMS-NS-025.png",
        "OHMS-NS-025.png",
        1704,
        382,
        "#f4f4f4"
      ]
    }
  ]
}
[/block]
These notification methods have been found most effective for high-urgency alerts. While the default is email, it can be less effective for high-urgency incidents as they can be lost in inboxes.

##Low Urgency Incidents

For low-urgency incidents, we recommend sending an email immediately following incident assignment. 

On the **Notification Rules** tab under **When a low-urgency incident is assigned to me**, select **zero minutes** and **email** as the method.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/59b7629-OHMS-NS-low-urgency.png",
        "OHMS-NS-low-urgency.png",
        1646,
        264,
        "#f4f4f4"
      ]
    }
  ]
}
[/block]
Since low-urgency alerts do not need immediate attention during off hours, setting to email can reduce alert fatigue.

Additional information on creating unique notification rules can be found in our Knowledge Base section on [High and Low Urgency Incidents](https://support.pagerduty.com/docs/service-settings#section-high-and-low-urgency-incidents). 

#Optional Settings

##When High-Urgency Incidents Change

You may also choose to be notified when incidents are acknowledged, escalated or resolved. These notification rules should be used with caution, as they can also create alert fatigue.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0bcd8e4-Screen_Shot_2018-12-11_at_4.02.59_PM.png",
        "Screen Shot 2018-12-11 at 4.02.59 PM.png",
        1232,
        384,
        "#efefef"
      ]
    }
  ]
}
[/block]
##On or Off-Call Notifications

In the **Before I go on-call or off-call** section you also have the option of receiving notifications for your on-call schedule.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bed1531-OHMS-NS-on-off-call.png",
        "OHMS-NS-on-off-call.png",
        1674,
        322,
        "#f5f5f5"
      ]
    }
  ]
}
[/block]
Take care to limit interrupt notifications to only those necessary for managing incidents, which will measurably improve the health of individuals and teams. The steps should be socialized throughout the organization as a standard best practice pattern to ensure that notifications are actionable. PagerDuty Expert Services can assist with an audit of current settings to ensure notifications policies are followed and can also mass-update notification settings to ensure conformity.