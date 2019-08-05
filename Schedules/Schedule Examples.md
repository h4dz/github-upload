---
title: "Schedule Examples"
excerpt: ""
---
[block:api-header]
{
  "title": "Example 1: Complex Irregular Schedules"
}
[/block]
This schedule is for teams that rotate 12-hour shifts, on for one week and then off for a few.
- [Ex1. Schedule Requirements](/docs/schedule-examples#section-ex1-schedule-requirements)
- [Ex1. Schedule Configuration](/docs/schedule-examples#section-ex1-schedule-configuration)
- [Ex1. Final Schedule](/docs/schedule-examples#section-ex1-final-schedule)

##Ex1. Schedule Requirements

This schedule has 6 users that alternate shifts every other week. One week, they work Sunday-Tuesday-Thursday-Saturday (STTS). The next week, they work Monday-Wednesday-Friday (MWF). There are a total of two six-week rotations, as everyone rotates through the MWF schedule, and one staggered by three weeks, where they work through STTS.

##Ex1. Schedule Configuration

Layer 1 rotates weekly with a handoff time at the beginning of the first time restriction. It will cover the STTS days by restricting on-call duty to specific *times-of-the-week*.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e5785f3-ComplexIrregular_img1.png",
        "ComplexIrregular_img1.png",
        1118,
        321,
        "#e8eee8"
      ]
    }
  ]
}
[/block]
Layer 2 rotates weekly with a handoff time at the beginning of its first time restriction. It will cover MWF by restricting on-call duty to specific times-of-the-week.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e6d8148-ComplexIrregular_img2.png",
        "ComplexIrregular_img2.png",
        1119,
        324,
        "#e9eee8"
      ]
    }
  ]
}
[/block]
##Ex1. Final Schedule
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b517c29-ComplexIrregular_img3.png",
        "ComplexIrregular_img3.png",
        1122,
        441,
        "#1a6366"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Example 2: Complex Schedule for 2 Users on a 2-Day Rotation with Separate Weekends"
}
[/block]
The example below shows a complex schedule for two users that are on a two-day rotation. They are on call in the evenings from 17:00 till 8:00 in the morning. On Saturday and Sunday, responders are on-call for 24 hours from 08:00 – 08:00 the next day.
- [Ex2. Schedule Requirements](/docs/schedule-examples#section-ex2-schedule-requirements)
- [Ex2. Configuration](/docs/schedule-examples#section-ex2-configuration)
- [Ex2. Final Schedule](/docs/schedule-examples#section-ex2-final-schedule)

##Ex2. Schedule Requirements
During the weekdays, User 1 and User 2 are only on call from 17:00 to 08:00. Then they take turns covering the weekends from Friday at 17:00 to Monday at 08:00. Shifts are:
- User 1 is on-call Tuesday and Wednesday from 17:00 to 08:00.
- User 2 is on-call Thursday and Friday from 17:00 to 08:00.
- User 1 is on-call Friday at 5pm to Saturday at 08:00 and Saturday at 08:00 to Sunday at 08:00.
- User 2 then is on-call Sunday at 8am to Monday 8am, and Monday 17:00 to Tuesday 08:00.

##Ex2. Configuration
Create four layers, each with its own weekly rotation that fulfills one of the requirements listed above.

The handoff time should be the day and time that the first restriction begins. The effective date of change should be the first date that that layer's restriction begins on. *This means that the date in Step 3 for each layer will be different.*
- User 1 is on-call Tuesday and Wednesday from 17:00 to 08:00.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/37abf2b-Complex2user_img1.png",
        "Complex2user_img1.png",
        1116,
        277,
        "#edeceb"
      ]
    }
  ]
}
[/block]
- User 2 is on-call Thursday and Friday from 17:00 to 08:00.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/427379c-Complex2user_img2.png",
        "Complex2user_img2.png",
        1114,
        274,
        "#edeceb"
      ]
    }
  ]
}
[/block]
- User 1 is on-call Friday at 5pm to Saturday at 08:00, and Saturday at 08:00 to Sunday at 08:00.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4a77cd3-Complex2user_img3.png",
        "Complex2user_img3.png",
        1114,
        260,
        "#edeceb"
      ]
    }
  ]
}
[/block]
- User 2 then is on-call Sunday at 8am to Monday 08:00, and Monday 17:00 to Tuesday 08:00.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3ff5d91-Complex2user_img4.png",
        "Complex2user_img4.png",
        1114,
        273,
        "#edecec"
      ]
    }
  ]
}
[/block]
##Ex2. Final Schedule
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9b9eec3-Complex2user_img5.png",
        "Complex2user_img5.png",
        1119,
        570,
        "#f1f0f0"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Example 3: Complex Split Shift Rotation"
}
[/block]
This example shows how to create a time-restricted 4-person rotation. Two users split each shift.
- [Ex3. Schedule Requirements](/docs/schedule-examples#section-ex3-schedule-requirements)
- [Ex3. Configuration](/docs/schedule-examples#section-ex3-configuration)
- [Ex3. Final Schedule](/docs/schedule-examples#section-ex3-final-schedule)

##Ex3. Schedule Requirements
These users are on-call between 00:00-10:00 with a shift length of 5 hours. After 5 hours, the next user comes on-call to cover the schedule until 10:00. 

##Ex3. Configuration
1. Add four users to the schedule in Step 1.
2. Click the Restrict on-call shifts to specific times option. Restrict the schedule to 00:00-10:00.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3f07110-Complex4user_img2.png",
        "Complex4user_img2.png",
        607,
        429,
        "#edf3ec"
      ]
    }
  ]
}
[/block]
3. Create a custom rotation type with a shift length of 12 hours. Set the handoff time to be halfway between the shift (05:00). 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/04a44d5-Complex4user_img1.png",
        "Complex4user_img1.png",
        1123,
        625,
        "#296071"
      ]
    }
  ]
}
[/block]
##Ex3. Final Schedule
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fe5feb4-Complex4user_img3.png",
        "Complex4user_img3.png",
        1119,
        367,
        "#f1f1f1"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Example 4: Complex Schedule with Restrictions"
}
[/block]
In this example, Alice and Fred trade off the early morning shift, Bob takes the morning, and Carol takes the evening shift during a four day week. Dave and Eve take shifts on the elongated weekend:
- Monday: Alice for 7 hours, then Bob for 6 hours, then Carol for 11 hours.
- Tuesday: Fred (7 hrs), Bob (6hrs), Carol (11hrs).
- Wednesday: Alice (7hrs), Bob (6hrs), Carol (11 hrs).
- Thursday: Fred (7 hrs), Bob (6hrs), Carol(11 hrs).
- Friday: Dave (12 hrs), Eve(12 hrs).
- Saturday: Dave(12 hrs), Eve (12 hrs).
- Sunday: Dave (12 hrs), Eve (12 hrs).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a365dd2-compsched1.png",
        "compsched1.png",
        522,
        417,
        "#dfdadf"
      ]
    }
  ]
}
[/block]
Dave and Eve are easy to schedule because they have consistent shifts. Create a layer for each remaining user and restrict on-call duty to specific times of the week, based on their scheduled shifts.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d721f18-compsched2.png",
        "compsched2.png",
        550,
        615,
        "#e8e8e7"
      ]
    }
  ]
}
[/block]
The result looks like this:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d6522b6-compsched3.png",
        "compsched3.png",
        610,
        188,
        "#efeee9"
      ]
    }
  ]
}
[/block]
You can overlap layers to make the schedule simpler. If you put the original Dave and Eve layer on the bottom, you can simplify some of the restrictions. Bob and Carol now only need to be restricted by time of day, and so on.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a33ec44-compsched4.png",
        "compsched4.png",
        600,
        501,
        "#ececeb"
      ]
    }
  ]
}
[/block]
##Ex4. Final Schedule
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b1f9b5b-compsched5.png",
        "compsched5.png",
        610,
        179,
        "#f1f1f1"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Example 5: Create Primary and Secondary On-Call Schedules"
}
[/block]
Creating primary and secondary schedules is helpful if the primary responder misses a notification. In this example we are using a primary and secondary schedule.  You may add more backup schedules to an escalation policy as needed.

- [Create a Primary On-Call Schedule](/docs/schedule-examples#section-create-a-primary-on-call-schedule)
- [Create a Secondary On-Call Schedule](/docs/schedule-examples#section-create-a-secondary-on-call-schedule)
- [Create an Escalation Policy](/docs/schedule-examples#section-create-an-escalation-policy)

##Create a Primary On-Call Schedule
1. Go to **Configuration → Schedules**, and click **New On-Call Schedule**.
2. Select a **Time Zone**.
3. Enter a schedule name.
4. Complete steps 1-3:
    1. Add **Users** from the drop-down list.
    2. Select the **Rotation Type** from the drop-down menu.
    3. Set the schedule **Start Date** and **Time**.
5. Preview the schedule and click **Create Schedule**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5a2ea5b-Primary-Secondary_img1.png",
        "Primary-Secondary_img1.png",
        1147,
        487,
        "#2c4671"
      ]
    }
  ]
}
[/block]
##Create a Secondary On-Call Schedule
1. Repeat the steps from the primary on-call schedule set up.
2. Add users in the secondary on-call order.
3. Complete steps 2 and 3 and click **Create Schedule**. Note that the secondary on-call rotation is different from the primary on-call rotation.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5b26678-Primary-Secondar_img2.png",
        "Primary-Secondar_img2.png",
        1128,
        473,
        "#2b4771"
      ]
    }
  ]
}
[/block]
##Create an Escalation Policy
1. Go to **Configuration → Escalation Policies**.
2. Click **New Escalation Policy**.
3. Enter an **Escalation Policy Name**.
4. Select **Primary Schedule** from the drop down list.
5. Enter **Escalation Time Out**, if applicable.
6. Click **Add a new Escalation Rule**.
7. Select **Secondary Schedule** from the drop down list.
8. Click **Save**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/47c5576-new_ep.png",
        "new_ep.png",
        987,
        635,
        "#eff0f1"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Example 6: Follow-the-Sun Schedule"
}
[/block]
The "follow-the-sun" schedule is commonly used for international teams in different timezones and ensures 24/7 coverage. This  schedule has three different sets of users on-call at different times of the day and the week. In this example we have a US team and an India team.
- [Ex6. Schedule Requirements](/docs/schedule-examples#section-ex6-schedule-requirements)
- [Base Schedule](/docs/schedule-examples#section-base-schedule)
- [Team 1 (US)](/docs/schedule-examples#section-team-1-u-s-)
- [Team 2 (India)](/docs/schedule-examples#section-team-2-india-)
- [Team 3 (Weekend)](/docs/schedule-examples#section-team-3-weekend-)
- [Ex6. Final Schedule](/docs/schedule-examples#section-ex6-final-schedule)

##Ex6. Schedule Requirements
In this schedule, we'll have three rotating shifts (or layers). The first layer, for users in the US, will consist of User 1 and User 2. They will be on-call during weekdays from 08:00 – 20:00 US Pacific Time (PT) and they will rotate on a weekly basis.

The India layer will be User 3 and User 4. They will be on-call weekdays starting at 20:00 PT until 08:00 PT the next day.

The third layer will cover the weekends, and all 4 users will be on it. The person on-call during the weekend will cover the whole weekend and will rotate weekly. For clarity's sake, let's define weekend to start at Friday 20:00 PT until Sunday 20:00 PT.

##Base Schedule
To create a schedule:
1. Go to **Configuration → Schedules**, then click **New On-Call Schedule**.
2. Enter a **Name** for the schedule and select a time zone. All times that you will select will be local to this time zone.

##Team 1 (US)
1. Add the US users (users 1 and 2) by clicking on the **Add User** link **Layer 1**.
2. Select **weekly** as the rotation type, set the **handoff time** to the beginning of your shift, and select **on-call shift to specific times...** checkbox to restrict on-call shifts for this team.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/69879b0-ScheduleFTS_img1.png",
        "ScheduleFTS_img1.png",
        1117,
        245,
        "#ecf2eb"
      ]
    }
  ]
}
[/block]
3. Restrict on-call duty to specific *times-of-the-day* and enter 08:00 to 20:00.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ebc4296-ScheduleFTS_img2.png",
        "ScheduleFTS_img2.png",
        604,
        433,
        "#edf3ec"
      ]
    }
  ]
}
[/block]
4. Click **Apply** to apply time restrictions to the layer.
[block:callout]
{
  "type": "info",
  "body": "You will not need to restrict this layer to weekdays as the weekend rotation in Layer 3 will replace weekend days on the final schedule. This follows the rule that the lowest layer has precedence over any higher layer.",
  "title": "Note"
}
[/block]
##Team 2 (India)
1. Click on the **Add Another Layer** button and add users 3 and 4 to **Layer 2**.
2. Select **weekly** as the rotation type and enter the start of the shift as the **handoff time**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/db2262f-ScheduleFTS_img3.png",
        "ScheduleFTS_img3.png",
        1117,
        238,
        "#24567a"
      ]
    }
  ]
}
[/block]
3. Restrict the *times-of-the-day* for the on-call shifts to 20:00 – 08:00 (8pm to 8am next day). 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/586a35c-ScheduleFTS_img4.png",
        "ScheduleFTS_img4.png",
        603,
        424,
        "#edf3ec"
      ]
    }
  ]
}
[/block]
4. Click **Apply** to restrict the layer.

##Team 3 (Weekend)
1. Click on the **Add Another Layer** button and add all 4 users to **Layer 3**.
2. Select **weekly** as the rotation type and set the **handoff time** to the beginning of the shift. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/83bf420-ScheduleFTS_img5.png",
        "ScheduleFTS_img5.png",
        1115,
        254,
        "#26547a"
      ]
    }
  ]
}
[/block]
3. Restrict the *times-of-the-week* for the on-call shifts to be from Friday 20:00 to Sunday 20:00.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1a43f43-ScheduleFTS_img6.png",
        "ScheduleFTS_img6.png",
        601,
        424,
        "#edf5ec"
      ]
    }
  ]
}
[/block]
4. Click **Apply** to restrict the layer.

##Ex6. Final Schedule
In the upper-right corner, click **Create Schedule** to create the schedule.
###Timeline View
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/265b1de-ScheduleFTS_img7.png",
        "ScheduleFTS_img7.png",
        1127,
        604,
        "#2c496c"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Example 7: Inverse Schedules on an Escalation Policy"
}
[/block]
If you have 2 or more users that rotate primary and secondary on-call shifts, you will want to create two on-call schedules and add each schedule to a separate level of an escalation policy.

Schedule example articles:
- [Ex7. Schedule Requirements](/docs/schedule-examples#section-ex7-schedule-requirements)
- [Ex7. Configuration](/docs/schedule-examples#section-ex7-configuration)
- [Ex7. Escalation Policy](/docs/schedule-examples#section-ex7-escalation-policy)

##Ex7. Schedule Requirements
This schedule has 2 users on-call. When User 1 is the first point of escalation, User 2 is the backup, receiving all incidents that User 1 does not respond to. When User 2 is the first point of escalation, User 1 is the backup, receiving all incidents that User 2 does not respond to.

##Ex7. Configuration
You will need to create 2 schedules. One for the escalation policy level 1, and the another for level 2.

###Schedule 1:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/79b9bca-InverseSchedules_img1.png",
        "InverseSchedules_img1.png",
        1125,
        383,
        "#ebebea"
      ]
    }
  ]
}
[/block]
###Schedule 2:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/93ead1f-InverseSchedule_img2.png",
        "InverseSchedule_img2.png",
        1120,
        382,
        "#ecebeb"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "You can use the **Copy this Schedule** button to clone a schedule, and then re-order the users. This option is under the :fa-cog: icon on the right side of the page.",
  "title": "Tip"
}
[/block]
##Ex7. Escalation Policy
Go to **Configuration → Escalation Policies** and either create a **New Escalation Policy**, or edit an existing one. Add Schedule 1 to Level 1 of the escalation policy. Then add Schedule 2 to Level 2 of the escalation policy.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/12a2654-InverseSchedules_img3.png",
        "InverseSchedules_img3.png",
        1125,
        673,
        "#ecf3ee"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Example 8: Schedule Users On-call Every Other Week"
}
[/block]
If you have a schedule where users are on-call every other week, you will need to create a layer within your schedule that reflects this type of rotation.
- [Ex8. Schedule Requirements](/docs/schedule-examples#section-ex8-schedule-requirements)
- [Ex8. Configuration](/docs/schedule-examples#section-ex8-configuration)
- [Ex8. Final Schedule](/docs/schedule-examples#section-ex8-final-schedule)

##Ex8. Schedule Requirements
This schedule has 4 users. 2 users are on-call during the weekdays. The other 2 are on call during the weekend. They rotate on a weekly basis. 

##Ex8. Configuration
Layer 1 will have weekday rotations. User 1 and 2 will rotate on a weekly basis with a handoff time Monday 00:00.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e54b65d-EveryOtherWeek_img1.png",
        "EveryOtherWeek_img1.png",
        1118,
        246,
        "#edecec"
      ]
    }
  ]
}
[/block]
Click **Add Another Layer** to create a second layer for the weekend. Layer 2 has Users 3 and 4 on a weekly rotation. Their handoff time is Saturday 00:00. Restrict this layer to the weekend.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b9caf1d-EveryOtherWeek_img2.png",
        "EveryOtherWeek_img2.png",
        1118,
        260,
        "#255677"
      ]
    }
  ]
}
[/block]
##Ex8. Final Schedule
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c7cf935-EveryOtherWeek_img3.png",
        "EveryOtherWeek_img3.png",
        1121,
        438,
        "#303f6b"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Example 9: Weekday — Weekend Schedule"
}
[/block]
A weekend/weekday schedule is any schedule which requires one rotation for the working week and another for the weekend. In this case, we use one layer for each group, respectively.

To get started, navigate to **Configuration → Schedules** and click **New On-Call Schedule**. Give your schedule a name.

##Layer 1: Weekday

The first layer is the weekday layer. Each member of this layer is on-call from 00:00 Monday morning to 00:00 Saturday morning in a weekly rotation. The easiest way to schedule this is to create a [basic weekly](/docs/schedules#section-create-a-basic-weekly-schedule) rotation where the handoff time is 00:00 with a weekly rotation.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/564b129-weekendweekdayschedule_img1.png",
        "weekendweekdayschedule_img1.png",
        1116,
        242,
        "#ecf1ec"
      ]
    }
  ]
}
[/block]
##Layer 2: Weekend
1. To create the weekend schedule, click **Add Another Layer** below the previous one. The second layer will be the *weekend* layer.
2. Add the layer members and set the rotation type as **daily** with a handoff time of **00:00** so users start at midnight.
3. Since this layer is only on Saturday and Sunday, you will need to click the check box to **Restrict on-call shifts to specific times**. Restrict on-call shift to *times-of-the-week* from Saturday 00:00 – Monday 00:00 to create the weekend rotation. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fee6850-a4d0456-weekdayweekendschedule_img4.png",
        "a4d0456-weekdayweekendschedule_img4.png",
        610,
        432,
        "#edf4ec"
      ]
    }
  ]
}
[/block]
Since the bottom layer takes precedence over other layers, the Final Schedule shows that User 1 and 2 take turns being on call Monday-Friday on a weekly basis. User 3 goes on call Saturday at 00:00. User 4 goes on call Sunday at 00:00. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/47140e2-weekdayweekendschedule_img5.png",
        "weekdayweekendschedule_img5.png",
        1115,
        429,
        "#f1f0f0"
      ]
    }
  ]
}
[/block]