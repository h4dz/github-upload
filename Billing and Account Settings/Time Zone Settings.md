---
title: "Time Zone Settings"
excerpt: ""
---
Most times in the PagerDuty web UI are rendered in the desired time zone of the user currently logged in. There are some exceptions to this on the User, Team, and System reports in [Advanced Analytics](doc:analytics#section-advanced-analytics). A user's time zone can be inherited from the account's default time zone. It’s important to note that a user profile can have a different default time zone than the account level time zone, and that all on-call schedules will be viewed in your selected time zone.
[block:callout]
{
  "type": "info",
  "body": "Any time-related information gathered via API calls, such as incident trigger times, will be displayed in UTC.",
  "title": "API Note"
}
[/block]

[block:api-header]
{
  "title": "Changing the Account-Level Time Zone"
}
[/block]
Only the Account Owner can change the account-level time zone.
1. Log in to PagerDuty as the Account Owner. 
2. Go to the **Configuration** menu and select **Account Settings**.
3. Under Account Details, select the Default Time Zone from the drop-down menu.
4. Click **Save changes**.
[block:api-header]
{
  "title": "Changing the User-Level Time Zone"
}
[/block]
1. Navigate to **My Profile** under the drop-down list in the top right corner of any page.
2. Click the **Edit icon** next to the time zone under your contact information.
3. Select the desired time zone from the drop-down list.
4. Click **Save changes**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d8aa8d8-time-zone-settings-edit-user.png",
        "time-zone-settings-edit-user.png",
        1682,
        448,
        "#f8f9f9"
      ]
    }
  ]
}
[/block]