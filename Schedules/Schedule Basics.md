---
title: "Schedule Basics"
excerpt: ""
---
On-call schedules are used to map out your coverage needs, and determine who will be notified when an incident is triggered. Only one user per schedule can be on-call at a time.

In a schedule with multiple layers, [the lowest layer always takes precedence](https://support.pagerduty.com/docs/schedules#section-schedule-layers). If a user on Layer 1 and Layer 2 overlap, the user on Layer 2 will be the one on-call for the period of their overlap. The user on Layer 1 is 'hidden' until the overlap ends; at that point, the user on Layer 1 will be on-call again. The last layer, then, essentially acts as an override for all layers that it overlaps.

You can use layers to clearly organize shifts visually, so that you can tell at-a-glance what days and hours a shift covers; the 'Final Schedule' shown at the bottom calculates the person on-call at any given moment and displays this exclusively.

It is also possible that [no one is on-call](https://support.pagerduty.com/docs/schedules#section-creating-schedule-gaps) during a given time period. If this is the case, then no incident will be created. Essentially, the schedule is set to 'off' during that time, until the next person starts their on-call shift, when incidents will be created again.
[block:api-header]
{
  "title": "Create a Schedule"
}
[/block]
Basic schedules are most often comprised of a single layer that allows you to add users to a schedule on a daily or weekly rotation.  A schedule layer is the foundation for more [complex schedules](doc:schedule-examples) that you can tailor to your team’s needs. 

To create a schedule layer: 

Navigate to **Configuration** and select **Schedules**. If you are making a new schedule, click on **New On-Call Schedule**. If editing an existing schedule, locate the schedule you want to edit, click the gear icon, and select **Edit**.
[block:callout]
{
  "type": "warning",
  "title": "Required User Permissions",
  "body": "The following roles can add, edit or delete on-call schedules:\n\n- Account Owner base role\n- Global Admin base role\n- Manager base role\n- Admin role\n\nIf you're not sure what role you have, or if you need your permissions adjusted, visit our sections on [Checking Your User Role](https://support.pagerduty.com/v1/docs/user-roles#section-checking-your-user-role) or [Changing User Roles](https://support.pagerduty.com/docs/user-roles#section-changing-user-roles)."
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "Any changes to the schedule apply to present and future dates or times only. Edits will not apply to schedules retroactively. If you want to revert a schedule to a previous state, it is recommended that you refer instead to [this article](/docs/editing-schedules#section-restore-a-schedule-to-a-previous-version)."
}
[/block]
## Step 1: Add Users

In the first section of the schedule you can [add or delete users](/docs/editing-schedules#section-adding-and-removing-users-on-schedules) from your schedule as needed. Users will move through the rotation in the top-to-bottom order they are listed in. If they are in the wrong rotation order, you can also drag and drop users into a different order.
[block:callout]
{
  "type": "warning",
  "title": "Required User Permissions",
  "body": "All users, with the exception of Stakeholders, can be added to schedules. \n\nIf you're not sure what role you have, or if you need your permissions adjusted, visit our sections on [Checking Your User Role](https://support.pagerduty.com/v1/docs/user-roles#section-checking-your-user-role) or [Changing User Roles](https://support.pagerduty.com/docs/user-roles#section-changing-user-roles)."
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f8141c9-schedule-basics-add-users.png",
        "schedule-basics-add-users.png",
        542,
        328,
        "#dfeedf"
      ]
    }
  ]
}
[/block]
##Step 2: Set up an on-call rotation

In this step you will set a **Rotation type** and a **Handoff time**, and you will have the option to **Restrict on-call shifts to specific times**:

###Rotation type 

Rotation Types determine how frequently the shifts on a layer rotate to the next user. Select your preferred Rotation type: daily, weekly, or custom.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/62f7172-basic-schedule-rotation-type.png",
        "basic-schedule-rotation-type.png",
        546,
        345,
        "#dddadb"
      ]
    }
  ]
}
[/block]
If the rotation type is **Custom**, enter the **Shift Length** and select hours, days, or weeks.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d49d4b5-basic-schedule-custom-rotation-type.png",
        "basic-schedule-custom-rotation-type.png",
        528,
        308,
        "#f5f2f1"
      ]
    }
  ]
}
[/block]
Refer to the **Final Schedule** section at the bottom of the page for a preview of what the schedule will look like after saving.

By default, a user will be on-call for the entire length of time determined by the Rotation Type. If you'd only like them to be on-call for for specific times during the day or week (i.e. after hours), please see our section on [schedule restrictions](https://support.pagerduty.com/docs/schedules#section-schedule-restrictions).

###Handoff time

The handoff time is the date and time when the user's on-call duties are handed off to the next user in the rotation for that layer. This time will be reflected in Step 3 as the **Start time for this layer** (when creating new schedules) or **Changes should take effect at** time (when editing existing schedules).

###Restrict on-call shifts to specific times *(optional)*

Clicking this checkbox will allow you to create shifts for only a few hours every day or specific days and times of the week.

If you restrict these to *times-of-the-day*, users will only be on call during the specified times every day (9am-5pm in the example below).

If you restrict these to *times-of-the-week*, users will only be on call during the specified times on the selected days of the week (9am-5pm on Monday, Wednesday, and Friday in the example below). 

Please visit our section on [Schedule Restrictions](https://support.pagerduty.com/docs/schedules#section-schedule-restrictions) to learn more about common use cases for this feature.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fa59304-basic-schedule-restrictions.png",
        "basic-schedule-restrictions.png",
        634,
        525,
        "#e7e8e6"
      ]
    }
  ]
}
[/block]
##Step 3: Start time for this layer

In the **Start time for this layer** section (when creating new schedules) or **Changes should take effect at** section (when editing existing schedules), set the date when would like the rotation specified in the schedule to start. The time will be set automatically by the **Handoff time** that you set in Step 2 (above).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6d95e57-basic-schedule-start-time.png",
        "basic-schedule-start-time.png",
        504,
        548,
        "#e6dfdf"
      ]
    }
  ]
}
[/block]
4. Check the **Final Schedule** section to ensure your shifts are correctly laid out. Click **Create schedule** (when creating a new schedule) or **Save changes** (when editing an existing schedule) and you're done!
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2726651-basic-schedule-final-schedule.png",
        "basic-schedule-final-schedule.png",
        1600,
        487,
        "#eddadc"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Optional Schedule Components"
}
[/block]

##Schedule Restrictions

PagerDuty's calendar will automatically distribute on-call shifts continuously (24 hours a day, 7 days a week) between users on a layer based on the rotation type and the selected starting point. Adding restrictions to a layer creates limitations on the times or days to which the schedule applies. 

This functionality allows you to achieve two common use cases: 

- [Creating gaps in schedules where no one is on call.](https://support.pagerduty.com/docs/schedules#section-creating-schedule-gaps)
- [Creating specific restrictions around the amount of time a user can be on call. ](https://support.pagerduty.com/docs/schedules#section-create-restrictions-for-on-call-shift-duration)

###Creating Schedule Gaps

Restrictions allow you to create gaps in coverage where no one is on call. This feature is most commonly used for coverage after business hours. If no one is on-call at a certain escalation level, the incident will immediately escalate to the next level of the escalation policy. If no one is on-call on the entire escalation policy, an incident will **not** be created.

If you try to create a new incident in the web UI on a service where no one is on-call, you will get an error message that the **Incident cannot be created**. Any trigger events sent to an integration where no one is on-call **will not trigger an incident**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f088308-schedule-basics-incident-not-assigned.png",
        "schedule-basics-incident-not-assigned.png",
        556,
        623,
        "#f6f7f4"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "If you want an incident to be created, but do not want anyone to be notified, or if you do not want any notification noise for an incident, this can be accomplished by setting up [support hours on your service](/docs/service-settings#section-step-1-configure-service) using low-urgency [Notification Rules](/docs/configuring-a-user-profile#section-notification-rules)."
}
[/block]
When setting up gaps in an after-hours schedule, special attention must be paid to setting the schedule starting point. In the example below, the schedule must cover Friday at 17:00 through Monday at 09:00, and 17:00 until 09:00 the rest of the week. In this case, Friday at 17:00 is a good starting point.

To create schedule gaps: 

1. Go to **Configuration → Schedules**.
2. Click the schedule to edit and click **Edit this Schedule**.
3. Select the **Rotation type** from the drop-down menu.
4. Click on the **Restrict on-call shifts to specific times** checkbox.
5. Select **Restrict on-call duty to specific times-of-the-week**.
6. Select the correct days and start times from the drop-down menu.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d654d51-schedule-basics-create-restrictions.png",
        "schedule-basics-create-restrictions.png",
        492,
        440,
        "#f2f3f1"
      ]
    }
  ]
}
[/block]
7. Click **Apply** to save.

The completed weekly schedule has gaps (meaning that nobody is on-call) from 09:00 to 17:00 Monday through Friday.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c13bc19-schedule-basics-gaps.png",
        "schedule-basics-gaps.png",
        3052,
        686,
        "#e9e7ee"
      ]
    }
  ]
}
[/block]
###Create Restrictions For On-Call Shift Duration

If you would like to limit the amount of time a user is on-call, instead of having a continuous 24/7 distribution between users, you will need to set up restrictions for the on-call duty duration.

To create restrictions for on-call duty duration:

1. Go to the **Configuration → Schedules**.
2. Click on the schedule to edit, then **Edit this Schedule**.
3. Select the **Restrict on-call shifts to specific times** checkbox to limit on-call duty to specific hours in the day.
4. Select **Restrict on-call duty to specific times-of-the-day** or **Restrict on-call duty to specific times-of-the-week**.
5. Set the **from** and **to** time and, if necessary, the day of the week, to restrict the on-call schedule to only apply during that time.

In the example below, we restricted the on-call user to be on call from 19:00-07:00 every weekday.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fde9216-schedule-basics-restrictions-example.png",
        "schedule-basics-restrictions-example.png",
        477,
        382,
        "#f4f5f4"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "Restricting on-call duty to specific dates and times creates gaps in schedule coverage. These gaps can remain unfilled, as with after-hours schedules. The gaps can also be filled with other layers, as in [follow-the-sun](/docs/schedule-examples#section-follow-the-sun-schedule) or [weekend/weekday](/docs/schedule-examples#section-weekday-weekend-schedule) schedules. Once the restrictions are set, the final schedule will show that the user is only on call from 19:00-07:00 every weekday. No one is on call from 07:00-19:00 or at any time during the weekend unless a second layer is created.",
  "title": "Note"
}
[/block]
##Schedule Layers

A schedule layer is comprised of a group of people who will rotate on-call responsibilities through the same shift. In a [basic weekly schedule](https://support.pagerduty.com/docs/schedules#section-create-a-schedule), you create a single layer where each member is on-call for one week, with a set day and time for transferring on-call responsibility.

PagerDuty’s calendar enables you to create multiple layers for one schedule. This feature can be useful for international companies wishing to create a [follow-the-sun schedule](/docs/schedule-examples#section-follow-the-sun-schedule), where each time zone can be grouped as a layer.

In cases when one schedule has multiple layers, the last layer created (the bottom layer on the schedule creation page) has precedence over the previous layer. This is illustrated in the example below.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/69c8254-schedule-basics-schedule-layer-prescedence.png",
        "schedule-basics-schedule-layer-prescedence.png",
        2308,
        685,
        "#d4d9d7"
      ]
    }
  ]
}
[/block]
Layers are also very commonly used for different weekday and weekend rotations. The example below has three separate layers. Layer 1 and Layer 2 have been shown as a weekday rotation and the bottom layer (Layer 3) is shown as a weekend rotation.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ffe0eb3-schedule-basics-layers-gaps.png",
        "schedule-basics-layers-gaps.png",
        2302,
        812,
        "#e9e9e9"
      ]
    }
  ]
}
[/block]
###End-Dating a Schedule Layer
If you would like to permanently delete a specific layer within an on-call schedule, you can set the end-date for that layer as today’s date with time set to whatever time you want that layer to end.

To end-date a schedule layer:
1. Go to **Configuration → Schedules**, then click on the schedule you want to edit.
2. Click **Edit this Schedule**.
3. Click **X** on the top right corner of the schedule layer you want to delete.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9fe92f4-basic-schedules-end-dating.png",
        "basic-schedules-end-dating.png",
        1163,
        450,
        "#f3ebea"
      ]
    }
  ]
}
[/block]
4. In the Schedule Layer Removal screen that appears, enter a date and time that you want to remove the schedule layer and click **Remove Layer**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/deb4b82-schedule-basics-remove-layer.png",
        "schedule-basics-remove-layer.png",
        568,
        251,
        "#f1f4f1"
      ]
    }
  ]
}
[/block]
5. Click **Save Changes**.
6. If you create an end-date for a schedule layer, you can return to the schedule and either undo or edit the end-date. Click to edit the on-call schedule so that you can edit or undo the end-date.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c374ab6-basic-schedules-edit-undo-end-date.png",
        "basic-schedules-edit-undo-end-date.png",
        1117,
        442,
        "#f3eef0"
      ]
    }
  ]
}
[/block]