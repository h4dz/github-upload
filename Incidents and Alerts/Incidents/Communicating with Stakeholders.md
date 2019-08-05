---
title: "Communicating with Stakeholders"
excerpt: ""
---
[block:api-header]
{
  "title": "Add and Notify Subscribers"
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "This feature is available to customers on our Enterprise plan and as part of the [Modern Incident Response](https://support.pagerduty.com/docs/pagerduty-modern-incident-response) package. Please contact our [Sales Team](https://www.pagerduty.com/contact-sales/) if you would like to upgrade to a plan with this feature."
}
[/block]
Adding subscribers lets you notify stakeholders who aren't directly involved with resolving the incident. These could be C-level executives concerned about the health of the company, or a Support team interacting with customers during an outage, for instance.
- [Add Subscribers to an Incident](/docs/communicating-with-stakeholders#section-add-subscribers-to-an-incident)
- [Subscriber Notifications](/docs/communicating-with-stakeholders#section-subscriber-notifications)
- [Remove Subscribers from an Incident](/docs/communicating-with-stakeholders#section-remove-subscribers-from-an-incident)

##Add Subscribers to an Incident
1. On the **Incidents** page, open an incident to view the details. Go to the **Subscribers** tab on the incident details page.
2. Select the team or specific users you’d like to add.
3. To notify the subscribers, enter a message in the **Status Update** field and click **Notify Subscribers**. Subscriber notifications will appear in the incident timeline.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1706553-Screen_Shot_2018-06-06_at_3.48.37_PM.png",
        "Screen Shot 2018-06-06 at 3.48.37 PM.png",
        2020,
        1550,
        "#f6f6f5"
      ]
    }
  ]
}
[/block]
##Subscriber Notifications
Once subscribed to an incident, stakeholders can expect to receive all subsequent manual status updates on that incident. Subscriber notifications will be sent the status update via their first email contact method and first SMS contact method, and their last push [contact method](/docs/configuring-a-user-profile#section-contact-information) in their user profile.
[block:callout]
{
  "type": "info",
  "body": "We currently do not offer customized notification rules to notify on a specific channel; if you do not wish to receive updates on a certain channel we recommend leaving that contact method blank."
}
[/block]
Notification emails contain the most information about an incident:
- Who sent the notification
- Incident number and description
- When the incident was opened
- The affected service
- To whom the incident is currently assigned
- Incident status
- A link to the incident status page

###Email Notification
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bbe3c2c-2fb7598-Subscribers_img2.png",
        "2fb7598-Subscribers_img2.png",
        660,
        475,
        "#f9f7f3"
      ]
    }
  ]
}
[/block]
###SMS Notification

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/27a3a04-ecd42c4-IMG_1769.png",
        "ecd42c4-IMG_1769.png",
        750,
        385,
        "#eaecf1"
      ]
    }
  ]
}
[/block]
###Push Notification

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9dc79d7-f938817-IMG_1771.png",
        "f938817-IMG_1771.png",
        748,
        250,
        "#8d939f"
      ]
    }
  ]
}
[/block]
##Remove Subscribers from an Incident 
Users assigned to the incident can remove subscribers from an incident, and subscribers can choose to unsubscribe themselves.

If you are a user assigned to the incident and you want to remove a subscriber:
1. Go to the **Incident Details** page.
2. Click on the **Subscribers** tab.
3. Under **Subscribers**, click on the name of the subscriber you want to remove.
4. Click on **Remove Subscriber**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0483cbb-Screen_Shot_2018-06-06_at_3.46.10_PM.png",
        "Screen Shot 2018-06-06 at 3.46.10 PM.png",
        1292,
        710,
        "#f2f4f2"
      ]
    }
  ]
}
[/block]
Subscribers can unsubscribe by: 

1. Going to the **Incident Status** page.
2. Click on the **Unsubscribe** button. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/041fbaf-Screen_Shot_2018-06-06_at_3.47.26_PM.png",
        "Screen Shot 2018-06-06 at 3.47.26 PM.png",
        1300,
        630,
        "#f8f8f8"
      ]
    }
  ]
}
[/block]
## Adding Subscribers at Scale

For repeatable, automated engagement of stakeholders, you can make use of a **Response Play**. Response plays are packaged incident actions, and **adding subscribers** is one component. You can read further about the response plays feature [here.](/docs/response-automation)

Effectively engaging with stakeholders should enable transparent communication around the potential impact and resolution progress of an incident. Proactive stakeholder communication can reduce or eliminate stakeholder inquiries about the incident status, which allows the incident responders to focus on resolving the incident at hand. Check out [our guide](/docs/how-to-effective-stakeholder-communications) to learn more about effective stakeholder communications.

# Other Features to Facilitate Incident Response

Instead of engaging stakeholders, which aren't directly involved in resolving the incident, you can: 

* [Add Responders](/docs/mobilizing-a-response) which enables you to receive **assistance from additional users** with an incident response. 
* [Escalating or Delegating an Incident](/docs/reassigning-and-delegating-incidents) which **re-assigns** the incident resolution responsibilities to another user.