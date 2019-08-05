---
title: "Editing Incidents"
excerpt: ""
---
[block:api-header]
{
  "title": "Merging Incidents"
}
[/block]
Merging related incidents into one incident streamlines the notification and resolution process when an incident is triggered. Merging incidents also enables you to consolidate the alert information into a single incident, helping responders identify the root cause and impact. Before merging incidents, make sure that you have enabled alerts and incidents for your service.

##How to merge incidents

If there are two or more triggered incidents on the incident dashboard, you can merge them into a single incident. When you merge them, they will appear as a single incident with multiple alerts.
1. Use the checkboxes to select the incidents
2. Next, select **Merge Incidents**.
3. In the popup, you can choose which incident you would like all of the alerts to be grouped under. When merging, you also have the ability to update the incident summary to more accurately reflect the problem. 
4. The incident dashboard will show a single incident. When you click to open the Incident and view its details, the alerts that you merged will be listed as the incident details.

You can also merge incident on the Incident details page by clicking **Merge Incidents** on the right side of the page. Then enter the incident number to merge into.

To view more granular details about what was sent you can also navigate to Show or Hide Details.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1199848-HideDetails.png",
        "HideDetails.png",
        2018,
        1921,
        "#f4f4f5"
      ]
    }
  ]
}
[/block]
##What happens when incidents are merged

When merging multiple incidents together, alerts will be consolidated into the selected incident. The other selected incidents will be resolved, with the reason for the resolution listed as "merged". These incidents will reference the target incident that you selected in the merge dialog.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0afa6fc-alerts_img3.png",
        "alerts_img3.png",
        1015,
        565,
        "#f5f5f4"
      ]
    }
  ]
}
[/block]
The deduplication key, called the alert_key, will not be changed, but it will move so that it is under a single incident with other deduplication keys.

If you are using a bidirectional integration such as the Slack integration, the merged incidents will display as resolved and reference the new target incident that contains all of the alerts.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ae511f6-Pasted_image_at_2016_10_24_02_55_PM.png",
        "Pasted image at 2016_10_24 02_55 PM.png",
        1576,
        708,
        "#ddc0c1"
      ]
    }
  ]
}
[/block]
When you merge the incidents, acknowledgers, assignees and responders from the source incidents are not merged. Instead, the target incident’s assigner, responder, and acknowledgers are preserved and they become the user(s) assigned to all alerts under that incident. These users may be viewed under the Response tab on the incident's page.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/68edf1c-Screen_Shot_2017-03-20_at_1.25.25_PM.png",
        "Screen Shot 2017-03-20 at 1.25.25 PM.png",
        1064,
        616,
        "#324c64"
      ]
    }
  ]
}
[/block]
##Moving alerts to another incident

If an alert is incorrectly merged, open up the Alert details page and select **Move to Another Incident** in the upper right-hand corner. A dialog box will prompt you to move the alert to its own new Incident, or you can optionally move the alert to an existing incident in PagerDuty:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6d0c036-MovetoAnotherIncident.png",
        "MovetoAnotherIncident.png",
        555,
        588,
        "#ecefec"
      ]
    }
  ]
}
[/block]
##Merged incidents and webhooks

If you are using webhooks, merging alerts into a single incident will send a resolve action through the webhooks for the source incidents with a resolve_reason of “merged.”

Webhooks will continue to update the target incident, but all past incidents that were merged into the target incident will be updated as resolved.

Likewise webhook updates will only continue to be sent for the service for that target incident; all past resolved incidents will remain resolved for other services. For example, if an incident from service A is merged into an incident for service B, only webhooks on service B will continue to be sent.

For incidents that were resolved when merged into the target incidents, the resolve webhook will trigger, if there are any that are configured. These incidents will contain reference to the new target incident ID: in the API response, the field will be merged_into_incident.
[block:api-header]
{
  "title": "Snooze an Incident"
}
[/block]
Snooze allows users to keep an incident in an "acknowledged" state for the following intervals of time: 1 hour, 4 hours, 8 hours, 24 hours or Other. If you choose "Other", the maximum length you can snooze an incident is one week (168 hours). As an incident responder, this means I can snooze an incident while I troubleshoot the problem — or go back to bed and avoid being woken up again by an issue that can wait until later!

##How do I snooze an incident?

You're only able to snooze acknowledged incidents. You can acknowledge an incident from either the web or mobile application. The following example outlines snoozing an incident in the web UI:

1. Acknowledge the incident.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bcf1fe9-0608a53-ack.png",
        "0608a53-ack.png",
        325,
        227,
        "#e1efe2"
      ]
    }
  ]
}
[/block]
2. Select **Snooze** and the length of time the incident should be snoozed.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b346486-ac6581f-Snooze_menu.png",
        "ac6581f-Snooze_menu.png",
        281,
        198,
        "#e7e7e7"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "If the [Add Responders](https://support.pagerduty.com/v1/docs/mobilizing-a-response#section-add-responders-to-an-incident) button has been used in an incident and an escalation policy was selected, snoozing will not prevent this escalation policy from escalating."
}
[/block]
The incident log will capture all snooze actions taken on an incident. If **Other** is selected, you will have the option to select a custom snooze time, snooze until a time tomorrow, or base your snooze on [support hours](/docs/service-settings#section-enable-urgencies) for that service.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ab02f62-a0c245d-Snooze_other.png",
        "a0c245d-Snooze_other.png",
        557,
        311,
        "#219a33"
      ]
    }
  ]
}
[/block]
Because he did not resolve the incident within the specified snooze timeframe, the incident returned to a triggered state and started notifying him again, following his notification rules. In the below example you can see that when the snooze timed out, the incident returned to a triggered state and re-notified the user. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/babcd32-snooze.png",
        "snooze.png",
        998,
        604,
        "#f6f6f6"
      ]
    }
  ]
}
[/block]
##What happens if I reassign a snoozed incident?
Reassigning a "snoozed" incident will cancel the snooze timer. The timeout setting will reset to the default timeout setting which is configured within the service from which the incident originated. 

##What happens if another user acknowledges the incident after I snooze the incident? 
If another user acknowledges the incident we will un-snooze the incident, and the un-acknowledgement timer will start again.

##Does the Snooze feature override the auto-resolution timeout on the Service?
Yes. It also restarts the timeout counter once the incident returns to an acknowledged or triggered state. 
[block:api-header]
{
  "title": "Add a Note to an Incident"
}
[/block]
Notes can be used to help responders resolve incidents quicker by including information or links related to the system that the event comes from.

You may want to add a note to an incident for other users to refer to. You can add this to an open or resolved incident.

##In Web UI

1. On the **Incidents** page, click on the name of an incident to open up the incident details.
2. Open the **Response** tab. Enter your note and click **Add Note**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c5d60e2-IncidentNotes_img1.png",
        "IncidentNotes_img1.png",
        1145,
        620,
        "#eff5ef"
      ]
    }
  ]
}
[/block]
##In Mobile App

1. Open the mobile app. Open the menu and tap either **Open Incidents** or **Resolved Incidents**
2. Tap on the incident you would like to add a note to to open its details.
3. On iOS, tap the More button at the bottom of the screen. On Android, tap the menu icon in the top right corner.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2ab3e35-IMG_0032.png",
        "IMG_0032.png",
        640,
        1136,
        "#1a2937"
      ]
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/608c72d-Screenshot_2015-09-23-10-57-36.png",
        "Screenshot_2015-09-23-10-57-36.png",
        1080,
        1920,
        "#1c2a39"
      ]
    }
  ]
}
[/block]
4. Tap Add Note.
5.Enter your note and tap Done on iOS orAdd on Android.

##Via Event Rules

Notes via Event Rules functionality is part of our [Event Intelligence product,](https://support.pagerduty.com/v1/docs/event-intelligence) which is purchased separately from the core PagerDuty platform.

Notes are added to incidents via the [Global Event Rules Engine](https://support.pagerduty.com/v1/docs/global-event-routing) workflows. Users first set specific criteria in which notes information will be added. Users can then detail which information or links they want to include in the note.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/902e51b-image6.png",
        "image6.png",
        1052,
        244,
        "#f4f4f4"
      ]
    }
  ]
}
[/block]
If the event is added to an incident, notes can be seen on that incident's details page. Notes added by event rules will list the first account user as the author.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2c71ef0-image2.png",
        "image2.png",
        522,
        223,
        "#f7f8f9"
      ]
    }
  ]
}
[/block]