---
title: "Incident Priority"
excerpt: ""
---
[block:api-header]
{
  "title": ""
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "This feature is only available on Enterprise plans and as part of the [Modern Incident Response](https://support.pagerduty.com/docs/pagerduty-modern-incident-response) package. If you are interested in getting on a pricing plan that includes this feature, please contact our [Sales Team](https://www.pagerduty.com/contact-sales/)."
}
[/block]
Incident priority allows the classification of incidents based on a level of prioritization. Just as alerts can have different levels of severity and notifications can have different levels of urgency, incidents can be classified into different levels of priority. Priority labels can be customized on a per account basis so you can match to your existing priority scheme that may be in use in other tools.

- [Enabling Incident Priority](#section-enabling-incident-priority)
- [Prioritizing an Incident](#section-prioritizing-an-incident)

#Enabling Incident Priority

Incident priority can be enabled for an entire account by any admin user. Once enabled, the UI of your incident dashboard will change to now include the Priority column.

To enable this feature:

1. Navigate to **Configuration → Incident Priorities**. 
2. Click **Enable Incident Priority Levels**.
3. You have the option to customize your priority labels and levels. You can classify incidents with up to 5 different priority levels.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0c1a82a-Priority_img1.png",
        "Priority_img1.png",
        293,
        432,
        "#3c9a17"
      ]
    }
  ]
}
[/block]
When you return to the **Incidents** page, you will see that the dashboard now contains a column for Priority. The priority is also displayed in an incident's details in both the web UI and mobile app. By default, past incidents will not have a priority, but you can append a priority to a past incident from the incident details page.

#Prioritizing an Incident

Incident priority can be set at the time of creation, or after the incident has been triggered.

##In the Web App
1. Navigate to the **Incidents** page and click **New Incident**.
2. Select the priority level that you would like from the dropdown:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/aa0f582-Priority_img2.png",
        "Priority_img2.png",
        555,
        626,
        "#f0f0f0"
      ]
    }
  ]
}
[/block]
3. After completing your other incident details, click **Create Incident**.

If you would like to add priority to incidents triggered using the REST API, you can retrieve the list of priorities for your account using our [REST API](https://v2.developer.pagerduty.com/v2/page/api-reference#!/Priorities/get_priorities). You can then include the appropriate priority code when posting the incident.

To edit an incident's priority after it has been triggered:
1. Find the incident that you would like to prioritize. Click the name of it to open the incident's details.
2. Click **Edit** next to the incident's priority and select the priority level from the dropdown.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f51ec64-priority_img3.png",
        "priority_img3.png",
        868,
        153,
        "#eaf6e8"
      ]
    }
  ]
}
[/block]
Priority cannot be set from the Events API at this time.

##In the Mobile App
1. Navigate to the **Open Incidents** screen and tap the overflow menu (top-right corner of screen).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8f46654-pasted_image_0-2.png",
        "pasted image 0-2.png",
        900,
        1600,
        "#2c383e"
      ]
    }
  ]
}
[/block]
2. Tap **New Incident...** 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d8aff77-pasted_image_0-1.png",
        "pasted image 0-1.png",
        900,
        1600,
        "#3a4a4d"
      ]
    }
  ]
}
[/block]
3. Tap **Priority** and select the priority level from the defined list.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/62d7ddf-pasted_image_0-2.png",
        "pasted image 0-2.png",
        900,
        1600,
        "#233632"
      ]
    }
  ]
}
[/block]
4.After completing your other incident details, click **Create**.

To edit an incident's priority after it has been triggered:
1. Find the incident that you would like to re-prioritize. Tap the incident name to open the details.
2. Tap the overflow menu and tap **Edit Priority**. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4f1c3ce-pasted_image_0.png",
        "pasted image 0.png",
        900,
        1600,
        "#293539"
      ]
    }
  ]
}
[/block]
3. Select the priority level from the screen. 
4. Tap **Confirm** in the confirmation dialog box to change the priority.