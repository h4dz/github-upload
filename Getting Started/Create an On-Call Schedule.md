---
title: "Create an On-Call Schedule"
excerpt: ""
---
On-call schedules are used to map out your coverage needs, and determine who will be notified when an incident is triggered. Only one user per schedule can be on-call at a time. 

In a schedule with multiple layers, the lowest layer always takes precedence. If a user on Layer 1 and Layer 2 overlap, the user on Layer 2 will be the one on-call for the period of their overlap. The user on Layer 1 is 'hidden' until the overlap ends; at that point, the user on Layer 1 will be on-call again. The last layer, then, essentially acts as an override for all layers that it overlaps.

You can use layers to more clearly organize shifts visually, so that you can tell at a glance what days and hours a shift covers; the 'Final Schedule' shown at the bottom calculates the person on-call at any given moment and displays this exclusively.

It is also possible that no one is on-call during a given time period. If this is the case, then no incident will be created; essentially, the schedule is set to 'off' during that time, until the next person starts their on-call shift, when incidents will be created again.

## Step 1: Creating an On-Call Schedule and Adding Users
[block:callout]
{
  "type": "warning",
  "title": "Required User Permissions",
  "body": "Admin, Manager base or team role, Global Admin base role or Account Owner base role.\n\nIf you're not sure what role you have, or if you need your permissions adjusted, visit our sections on [Checking Your User Role](https://support.pagerduty.com/v1/docs/user-roles#section-checking-your-user-role) or [Changing User Roles](https://support.pagerduty.com/docs/user-roles#section-changing-user-roles)."
}
[/block]
To begin, make sure that you have already invited the users that you want to include in your on-call schedule.

To create an on-call schedule:

1. Go to the **Configuration** menu and select **Schedules**.

2. Click **New On-Call Schedule** to create a new schedule, or click on an existing on-call schedule and click **Edit this Schedule**.

3. In **Step 1: Add users**, select the user you would like to add from the drop-down menu. Repeat this step until you have added the all the users you want in the schedule layer.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/38f37a9-Add_Users.png",
        "Add Users.png",
        580,
        190,
        "#21979c"
      ]
    }
  ]
}
[/block]
4. To change the order of the rotation, just click on a user and drag them up or down in the list. Once a schedule has been saved, you can still reorder the user rotation, but it will not change the rotation in the past.

## Step 2: Setting the Rotation Type and Adding Restrictions

Rotation Types determine how the on-call schedule rotation is set up. Rotation types can be set as daily, weekly, and custom. PagerDuty’s calendar will automatically distribute on-call shifts evenly between users on a layer based on the rotation type and starting point selected. Adding restrictions to a layer creates limitations on the times or days to which the schedule applies. By default, during a shift each person is on-call continuously (24 hours a day, 7 days a week). However, you can restrict the on-call duty by adding restrictions to your on-call schedule.

To set up the rotation type:

1. In **Step 2: Set up an on-call rotation**, select the **Rotation type** from the drop-down menu.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/654571b-Rotation_Type.png",
        "Rotation Type.png",
        500,
        190,
        "#edeeed"
      ]
    }
  ]
}
[/block]
2. If the rotation type is **Custom**, enter the **Shift length** time and select hours, days, or weeks from the drop-down list.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c398d66-Custom_Rotation_Type.png",
        "Custom Rotation Type.png",
        505,
        230,
        "#ebecec"
      ]
    }
  ]
}
[/block]
To add restrictions:

1. In **Step 2: Set up an on-call rotation**, select **Restrict on-call shifts to specific times** to limit on-call duty to specific hours in the day.

2. Select **Restrict on-call duty to specific times-of-the-day** or **Restrict on-call duty to specific times-of-the-week**. Restricting based on the time of day sets the on-call user to be on-call for the same hours every day of the week. Restricting based on specific times of the week allows you to set different on-call hours depending on the day of the week.

3. Set the **from** and **to** time and, if necessary, the day of the week, to restrict the on-call schedule to only apply during that time.

4. In the below example, we restricted the on-call user to be on-call from 1900-0700 every weekday. Once the restrictions are set, the final schedule will show that the user is only on-call from 1900-0700 every weekday. No one is on-call from 0700-1900 unless a second layer is created.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/53fb366-on-call2.png",
        "on-call2.png",
        470,
        438,
        "#ececea"
      ]
    }
  ]
}
[/block]
## Step 3: Set the Start Time & Date

When you create a new schedule, PagerDuty will ask you to "Set the schedule starting point" and will default to the current time and date. Follow the instructions below to set the schedule starting point to something other then the default.

1. In **Step 3: Start time for this layer**, set the schedule starting point. Notice that the default starting point is today at the current time.

2. To adjust the start date, click on the **date field** and select the date. Remember that the date must be in the future.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a19e2b1-Start_Time__Date.png",
        "Start Time & Date.png",
        525,
        320,
        "#e9e9e9"
      ]
    }
  ]
}
[/block]
3. To adjust the start time, Click on the **time field** and select the correct time from the drop-down list.

4. Click **Create Schedule**.