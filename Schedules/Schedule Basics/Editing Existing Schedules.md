---
title: "Editing Existing Schedules"
excerpt: ""
---
As new users join and other users leave your on-call rotations, you will need to edit your on-call schedules so that the right people are on-call and notified at the right times.

Any changes made to a schedule (including adding and removing users) won't affect the historical record of that schedule — changes will only apply to future dates and times. Make sure to check the effective date for changes to make sure that the schedule rotates on the right date and time when you add or remove a user.
[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "Any changes made to a schedule (including adding and removing users) won't affect the historical record of that schedule — changes will only apply to future dates and times. Make sure to check the effective date for changes to make sure that the schedule rotates on the right date and time when you add or remove a user. If you want to revert a schedule to a previous state, please visit [this section](/docs/editing-schedules#section-restore-a-schedule-to-a-previous-version)."
}
[/block]
*If you are creating a schedule for the first time, please visit our article on [Schedule Basics](/docs/schedules).*
[block:api-header]
{
  "title": "Adding Users to Existing Schedules"
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "Required User Permissions",
  "body": "All users, with the exception of Stakeholders, can be added to schedules. \n\nIf you're not sure what role you have, or if you need your permissions adjusted, visit our sections on [Checking Your User Role](https://support.pagerduty.com/v1/docs/user-roles#section-checking-your-user-role) or [Changing User Roles](https://support.pagerduty.com/docs/user-roles#section-changing-user-roles)."
}
[/block]
To add additional users to an existing on-call schedule:

1. Navigate to  **Configuration** and select **Schedules**.
2. Click the gear icon for an existing on-call schedule and select **Edit**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9216f91-editing-schedules-edit.png",
        "editing-schedules-edit.png",
        1642,
        364,
        "#ecf0ec"
      ]
    }
  ]
}
[/block]
3. Click **Select a User** to choose a user's name from the dropdown or search for it to add a user to the on-call schedule layer. When you click the user’s name, it will add them to the schedule.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5863c3d-156f136-SchedulesAddingUsers_img2.png",
        "156f136-SchedulesAddingUsers_img2.png",
        415,
        325,
        "#edefef"
      ]
    }
  ]
}
[/block]
4. Repeat until required users are added. Users will move through the rotation in the top-to-bottom order they are listed in. If they are in the wrong rotation order, you can also drag and drop users into a different order.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bbae5b8-5c2ad00-SchedulesAddingUsers_img3.png",
        "5c2ad00-SchedulesAddingUsers_img3.png",
        426,
        248,
        "#edeced"
      ]
    }
  ]
}
[/block]
5. Click **Save Changes** in the upper right hand corner of the screen.

##Removing Users From Existing Schedules

To permanently remove a user from an on-call schedule:

1. Navigate to  **Configuration** and select **Schedules**.
2. Click the gear icon for the existing on-call schedule and select **Edit**.
3. Click the **X** next to the user's name that you want to remove.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7ef8f61-1d70d8e-SchedulesAddingUsers_img5.png",
        "1d70d8e-SchedulesAddingUsers_img5.png",
        419,
        317,
        "#089409"
      ]
    }
  ]
}
[/block]
4. Click **Save Changes** in the upper right hand corner.
[block:api-header]
{
  "title": "Create and Delete Overrides"
}
[/block]
Overrides are used to make manual one-time adjustments to on-call schedules. Overrides are most commonly used when a user is sick, goes on vacation, or would like to swap on-call periods with someone else. 

Scheduling an override creates an override layer over the existing schedule. Scheduled overrides are displayed beneath your schedule layers, as the lowest layer before the Final Schedule (the lowest layer always takes precedence). 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9dcff4a-editing-schedules-override-layer.png",
        "editing-schedules-override-layer.png",
        1514,
        962,
        "#e8ebeb"
      ]
    }
  ]
}
[/block]
You can create overrides within the [PagerDuty web UI](https://support.pagerduty.com/docs/editing-schedules#section-create-overrides-in-the-web-ui), or you can create them [using the REST API](https://support.pagerduty.com/docs/editing-schedules#section-create-overrides-using-the-rest-api). 
[block:callout]
{
  "type": "warning",
  "title": "Required User Permissions",
  "body": "All users, with the exception of Restricted Access, Observers and Stakeholders, can create Overrides. \n\nIf you're not sure what role you have, or if you need your permissions adjusted, visit our sections on [Checking Your User Role](https://support.pagerduty.com/v1/docs/user-roles#section-checking-your-user-role) or [Changing User Roles](https://support.pagerduty.com/docs/user-roles#section-changing-user-roles)."
}
[/block]
##Create Overrides in the Web UI

There are two places to schedule overrides on existing schedules in PagerDuty: 

- [On a specific schedule shift.](https://support.pagerduty.com/docs/editing-schedules#section-override-a-specific-schedule-shift)
- [On any span of time on a schedule.](https://support.pagerduty.com/docs/editing-schedules#section-override-any-span-of-time-on-a-schedule)

###Override a specific schedule shift

Scheduling an override by clicking directly on the shift you'd like to override will pre-populate the override window with the effective dates and times, without you having to manually punch them in.

1. Navigate to **Configuration** and select **Schedules**.
2. From the main **Schedules** page or from the individual schedule's edit page, click directly on the shift that you would like to override. If need be, you can tab forward by days, weeks, and months to locate the shift you would like to override.
3. The **Schedule an Override** window will be pre-populated with the times of the shift that you just clicked. Make the necessary changes to the **Person** you're adding for the override and click **Create Override** and the override will immediately appear on the schedule..
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9dd6fe7-editing-schedules-override-web-ui.png",
        "editing-schedules-override-web-ui.png",
        1111,
        724,
        "#f4f6f4"
      ]
    }
  ]
}
[/block]
###Override any span of time on a schedule

1. Navigate to **Configuration** and select **Schedules**.
2. Click the gear icon for the desired on-call schedule and select **Schedule an Override**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/74b4c1b-editing-schedules-schedule-override.png",
        "editing-schedules-schedule-override.png",
        2140,
        572,
        "#e3e6e6"
      ]
    }
  ]
}
[/block]
3. Or you can click into a schedule and select **Schedule an Override**
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d1b44b4-editing-schedules-override-in-schedule.png",
        "editing-schedules-override-in-schedule.png",
        2224,
        426,
        "#f3f2f2"
      ]
    }
  ]
}
[/block]
4. The override window will be a pop-up. Select the **Person** and **start/end times** of the override. Click **Create Override**.

##Create Overrides Using the REST API

An example Python script to schedule overrides for a user going on vacation can be found here: [vacation_overrides.py](https://github.com/PagerDuty/public-support-scripts/tree/master/overrides_bulk_operations).

To learn more about how to interact with the PagerDuty API, we recommend checking out the collection of scripts our community has created on our [Knowledge Base](/docs/third-party-tools). Our developer docs also provide more information on [creating](https://v2.developer.pagerduty.com/v2/page/api-reference#!/Schedules/post_schedules_id_overrides) and [deleting](https://v2.developer.pagerduty.com/v2/page/api-reference#!/Schedules/delete_schedules_id_overrides_override_id) overrides using the REST API.

##Delete an Override

You can delete upcoming overrides on your schedule in the event that the override is no longer needed. If an override is deleted during the middle of the scheduled shift, the regular schedule will resume from the time of the override's deletion. You cannot delete past overrides; only present or future ones.

To delete an override:

1. While on the **Schedules** page, click on the name of the schedule *or* select **View** after clicking on the gear for the schedule you would like to change.
2. In the **Upcoming Overrides** list, click the **X** to delete the override.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5ca26a7-editing-schedules-upcoming-overrides-delete.png",
        "editing-schedules-upcoming-overrides-delete.png",
        514,
        636,
        "#e2e4de"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Pause or Deactivate an On-call Schedule"
}
[/block]
Sometimes you might want to stop a schedule from being used without deleting it.

For example:

- If the schedule is a draft which you are not ready to implement. (Note, however, that you can set an effective date for future changes without deactivating your current schedule)

- If the schedule needs to be used regularly but only for special events, such as on-call shadowing.

To prevent an on-call schedule from being used, you will want to either remove the schedule from any escalation policies it is assigned to, or [change the escalation policy used by your services](https://support.pagerduty.com/docs/escalation-policy-vs-schedule#section-pause-or-deactivate-an-on-call-schedule) to one that does not use the schedule.

##Option 1: Remove a Schedule from an Escalation Policy

The right sidebar will display any escalation policies where the schedule is in use.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e4dd366-editing-schedules-ep-location.png",
        "editing-schedules-ep-location.png",
        510,
        844,
        "#e6e8e3"
      ]
    }
  ]
}
[/block]
Click on the **escalation policy** you want to remove the schedule from, then click **Edit Escalation Policy** on the top right corner of the page.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bdd51c6-editing-schedules-edit-ep-button.png",
        "editing-schedules-edit-ep-button.png",
        524,
        104,
        "#f2f2f2"
      ]
    }
  ]
}
[/block]
Find your **schedule** in the **Notify the following users or schedules** field, then click the **X button** on the schedule object to remove it from the rule.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/82e0f71-editing-schedules-delete-schedule-from-ep.png",
        "editing-schedules-delete-schedule-from-ep.png",
        886,
        296,
        "#f0efef"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "If the schedule is the only target (person or schedule) in the escalation rule, you will need to click the **X button** on the rule to delete the entire rule, as each rule must contain at least one target.",
  "title": "Note"
}
[/block]

[block:image]
{
  "images": [
    {
      "image": []
    }
  ]
}
[/block]
Click **Save** when you are done, and repeat this process for any additional escalation policies this schedule is used by.

##Option 2: Change the Escalation Policy for a Service

Please visit our article on [Escalation Policies and Services](https://support.pagerduty.com/docs/escalation-policy-vs-schedule#section-pause-or-deactivate-an-on-call-schedule) for instructions on how to change the escalation policy used by a service. This will ensure that incidents triggered for the service do not alert the schedule you want to deactivate.
[block:api-header]
{
  "title": "Restore a Schedule to a Previous Version"
}
[/block]
If you or another user alters a schedule in an undesired way, you can quickly revert a schedule back to a previously saved version. This feature also allows you to see when each saved change was made.

To revert a schedule:

1. Click on **Configuration → Schedules**.
2. Click on the name of the schedule that you wish to revert to open its details.
3. On the right hand side of the page, click on **Revert this Schedule** to view the recent changes made to that schedule.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9bf1324-editing-schedules-revert-schedule.png",
        "editing-schedules-revert-schedule.png",
        526,
        846,
        "#ededef"
      ]
    }
  ]
}
[/block]
4. Once you select one of the options from the dropdown, you will be brought to the Edit Schedule page for that version of the schedule. From here you may make additional edits, or click on **Revert Schedule** in the upper right corner of the page.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/beb808b-editing-schedules-revert-final.png",
        "editing-schedules-revert-final.png",
        2208,
        258,
        "#eeece1"
      ]
    }
  ]
}
[/block]
##Limitations
Currently only changes made to the schedule layers are saved and can be reverted. Overrides will *not* be affected if you revert a schedule. For now, the user's name making each change is omitted. However, this is something being considered for a later release.