---
title: "Escalation Policy Basics"
excerpt: ""
---
Escalation policies connect services to individual users and/or schedules and they ensure the right people are notified at the right time. A service can only have one escalation policy, though an escalation policy can be associated with multiple services. Escalation policies are designed to notify a single target at a time until one individual acknowledges the incident. If you would like to notify more than one person at the same time, please visit our section on [notifying multiple users at once](https://support.pagerduty.com/docs/escalation-policies#section-notifying-multiple-users-at-once-regardless-of-their-on-call-status).
[block:api-header]
{
  "title": "Create an Escalation Policy"
}
[/block]
When you are first configuring your PagerDuty account, you will have a **Default** escalation policy. The *Account Owner* will be the only target on the default escalation policy, though this can be changed at any time.
[block:callout]
{
  "type": "warning",
  "body": "The following roles can add/edit/delete escalation policies:\n\n- Admin roles \n- Manager base roles\n- Global Admin base roles\n- Account Owner base roles \n\nIf you're not sure what role you have, or if you need your permissions adjusted, visit our sections on [Checking Your User Role](https://support.pagerduty.com/v1/docs/user-roles#section-checking-your-user-role) or [Changing User Roles](https://support.pagerduty.com/docs/user-roles#section-changing-user-roles).",
  "title": "Required User Permissions"
}
[/block]
To create an escalation policy:

1. Navigate to **Configuration** and select **Escalation Policies**.
2. Click **New Escalation Policy**.
3. Name your escalation policy. Add a description (optional).
4. Select the [target(s)](https://support.pagerduty.com/docs/escalation-policies#section-escalation-targets-and-limitations) you want to notify when an incident is triggered:
  * Select a **user(s)** if you always want that person(s)to be notified when an incident is assigned and/or escalated to an escalation level.
  * Select an **on-call schedule(s)** if you want to notify the user who is on-call from that schedule when an incident is assigned and/or escalated to an escalation level.
**Note**: If you select more than one user/schedule, each user and/or schedule will be [notified at the same time](https://support.pagerduty.com/docs/escalation-policies#section-notify-multiple-users-at-once) per escalation level.
5. You can then add a second [level](https://support.pagerduty.com/docs/escalation-policies#section-escalation-levels) to the escalation policy, which will serve as a secondary line of responders who will be notified in the event that no one in the first level responds. To do this, enter the number of minutes that should pass before the incident escalates to the next level in the **escalates after ___ min.** field. This time period is called the escalation timeout. Incidents will not escalate if they are acknowledged or resolved before the timeout is reached.
6. Then click **Add a new Escalation Rule** to create the second level.
7. Select targets for the second escalation rule.
8. Configure additional escalation rules as required.
9. Click **Save**. 
[block:callout]
{
  "type": "success",
  "title": "Recommended",
  "body": "We suggest configuring your policy to repeat. To do this, check the box next to **If no one acknowledges, repeat this policy __**. Then, select the number of times to repeat. An escalation policy can be repeated up to 9 times."
}
[/block]
##Escalation Policy Example

In the example below, if an on-call user in the **Primary On-Call Schedule** schedule does not acknowledge an incident in 30 minutes, it will escalate to Jason Collison. The escalation timeout at the second level is also 30 minutes. Jason will have 30 minutes to acknowledge the incident before it escalates and starts over from the beginning of the policy. This escalation policy is set to repeat 9 times.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/924b543-ep-basics-ep-example.png",
        "ep-basics-ep-example.png",
        984,
        485,
        "#f9fafa"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Escalation Targets and Limitations"
}
[/block]
You can select users or schedules as targets on an escalation policy:  

* **User Targets**: Select users as targets if you always want a specific person/persons to be notified when an incident is assigned and/or escalated to an escalation level.
* **Schedule Targets**: Select on-call schedules as targets if you want to notify the user who is on-call from that schedule when an incident is assigned and/or escalated to an escalation level. For more information on common use cases, please visit our article on [Escalation Policies and Schedules](https://support.pagerduty.com/docs/escalation-policies-and-schedules).

When an incident triggers, we'll attempt to notify responders at the first level of the escalation policy. If the incident is not acknowledged within the escalation timeout period, it will escalate to next escalation level, and so on down the line.

If nobody is on-call in the first level, we will assign the incident to the on-call responder at the subsequent escalation level.
[block:callout]
{
  "type": "warning",
  "body": "An incident follows the escalation policy as it was at the time the incident triggered. Any changes to the escalation policy made after an incident triggers will **not** affect open incidents (triggered or acknowledged).",
  "title": "Important Note"
}
[/block]
###Limits on Escalation Policies

* You can add up to 20 escalation rules to an escalation policy.
  * You have the option to repeat an escalation policy 9 times. Once an escalation policy reaches the amount of loops configured, the incident will stay assigned to the last user and will not continue to notify once it has cycled through all of the responder's contact methods.
  * Notifying too many users at once runs the risk of creating confusion about who owns an incident. With this is mind, [multi-user notifications](https://support.pagerduty.com/docs/escalation-policies#section-notify-multiple-users-at-once) on each escalation rule are limited to 50 users or schedules on Enterprise plans or accounts with Modern Incident Response, 10 on Platform Business plans, and 5 on Platform Team and Starter plans. [This topic](https://community.pagerduty.com/t/notifications-suggestions-on-when-to-notify-one-vs-many/453) addresses best practices about when to notify one user vs. many users.
  * The minimum escalation timeout is 1 minute if there is a single target on an escalation rule. Alternatively, if there is more than one target in an escalation level the minimum escalation timeout is 5 minutes. These restrictions are displayed in the web UI.
[block:api-header]
{
  "title": "Escalation Levels"
}
[/block]
Escalation policies are made up of levels that allow you to escalate incident notifications to different users and/or on-call schedules in the case that no one responds. An escalation policy should have at least two levels, with the option of adding more. Escalation levels can also be used to achieve more [complex use cases involving schedules](https://support.pagerduty.com/docs/escalation-policies-and-schedules#section-escalation-policy-and-schedule-use-cases). 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6a29adf-escalation-policy-basics-levels.png",
        "escalation-policy-basics-levels.png",
        1688,
        732,
        "#f7f6f6"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Notify Multiple Users at Once"
}
[/block]
An escalation policy is designed to engage one person in incident response, and it will escalate until one person has responded. Once one person has responded, the escalation policy will stop escalating, and no further notifications will be sent. 

Multi-user notifications can notify multiple users at once when an incident is triggered or escalated, and can be configured within an escalation policy. There are three methods of configuring multi-user notifications based on your intended use-case:

- Notifying multiple *users* at once regardless of their on-call status. This method is covered [below](https://support.pagerduty.com/docs/escalation-policies#section-notifying-multiple-users-at-once-regardless-of-their-on-call-status).
- Notifying multiple users and/or groups at once *based on a specific span of time*. For instance, if you want more than one person to be notified during the weekend or after business hours. This method is also covered in our article [Escalation Policies and Schedules](https://support.pagerduty.com/docs/escalation-policies-and-schedules#section-notifying-multiple-users-at-once-based-on-a-span-of-time).
- Notifying a Secondary on-call user when a Primary on-call user does not respond based on their *schedule* and *escalation level*. This method is covered in our article [Escalation Policies and Schedules](https://support.pagerduty.com/docs/escalation-policies-and-schedules#section-notify-a-secondary-on-call-responder-when-the-primary-does-not-respond).
[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "To create packages of incident actions that allow you to assemble a response team of multiple on-calls and/or escalation policies independently, you can also use a [response play](https://support.pagerduty.com/docs/response-automation) to mobilize a coordinated [response](https://support.pagerduty.com/v1/docs/how-to-mobilizing-coordinated-responses)."
}
[/block]
##Notifying Multiple Users at Once Regardless of Their On-Call Status

To notify two or more users at once regardless of their on-call status, you will want to set up an escalation policy with multiple users on the same escalation level:

1. Go to **Configuration** → **Escalation Policies**.

2. Click **New Escalation Policy** to create a new escalation policy, or click an existing escalation policy's gear icon and then **Edit** to edit an existing one.

3. Click in the field below **Notify the following users or schedules** and select the on-call users you want to notify at the same time when an incident is triggered or escalated. 

In the example below, Harriet Spy and Rocko Wallaby will be notified at the same time since they are both in escalation level 1. If neither of them respond within 30 minutes, it will then escalate to escalation level 2 and Donatello Turtle will then be notified. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7d98de6-escalation-policy-basics-escalation-level.png",
        "escalation-policy-basics-escalation-level.png",
        1146,
        792,
        "#f4f2f2"
      ]
    }
  ]
}
[/block]
4. Click **Save** and you're done!
[block:callout]
{
  "type": "danger",
  "title": "FAQ: Can I use a schedule on its own to achieve multi-user notifications?",
  "body": "No. Please visit [Why Schedules Alone Are Ineffective For Multi-User Notifications](https://support.pagerduty.com/docs/escalation-policies-and-schedules#section-why-schedules-alone-are-ineffective-for-multi-user-notifications) for more information. This section covers essential concepts to understand, and how to properly configure multi-user notifications."
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "If you have Live Call Routing enabled to Connect Directly and there is more than one responder on an escalation level, PagerDuty will randomly cycle through all responders on at that level. If an incident triggers via Live Call Routing (if either no one answers, or you've selected \"Leave a Message\"), however, all users on an escalation level can expect to receive notifications via their configured notification methods.",
  "title": "Note"
}
[/block]