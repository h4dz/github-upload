---
title: "Teams"
excerpt: ""
---
Teams allow users to customize the UI so that they only see information relevant to specific escalation policies, or groups of escalation policies. For example, a DevOps team member may only want to see the users, incidents, schedules and services associated with DevOps escalation policies. Likewise, a support team manager may only want to see information relevant to his or her team.

Teams are available on Platform Business and Enterprise plans. Please [contact our sales team](mailto:sales@pagerduty.com) if you would like to upgrade to a plan featuring Teams.

## Create a Team
[block:callout]
{
  "type": "warning",
  "title": "Required User Permissions",
  "body": "Manager, Global Admin or Account Owner roles on plans with [Advanced Permissions](https://support.pagerduty.com/docs/advanced-permissions).\n\nIf you're not sure what role you have, or if you need your permissions adjusted, visit our sections on [Checking Your User Role](https://support.pagerduty.com/v1/docs/user-roles#section-checking-your-user-role) or [Changing User Roles](https://support.pagerduty.com/docs/user-roles#section-changing-user-roles)."
}
[/block]
It is recommended that you create schedules and escalation policies before creating a Team. For guidance on the basics of configuring your account, see the PagerDuty quick start guide.

1. Go to the **Configuration** menu and select **Teams**.

2. Click **New Team**. Name the team and select the appropriate escalation policy(s). Then click **Save**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6702bd7-CreatingTeams_img2.png",
        "CreatingTeams_img2.png",
        992,
        316,
        "#3b6454"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "You can add up to 100 unique escalation policies per team.",
  "title": "Note"
}
[/block]
## Editing Teams

You can view all teams under **Configurations** → **Teams**.

You can edit or delete an existing team by clicking on the :fa-cog:. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9afc8cd-CreatingTeams_img3.png",
        "CreatingTeams_img3.png",
        1044,
        326,
        "#f6f6f5"
      ]
    }
  ]
}
[/block]
###Add Users or Escalation Policies to a Team

To manually add a user or escalation policy to a team, click the :fa-cog: and select **Edit**. Type the user's name or escalation policy name into the **Users** or **Escalation Policies** fields, select the name when it populates and then click **Save**. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/43e7eff-teams-add-user-esc-policy.png",
        "teams-add-user-esc-policy.png",
        1792,
        648,
        "#f8f5f5"
      ]
    }
  ]
}
[/block]
###Edit Team Roles 

To change a user's role within a Team, go to **Configuration** → **Teams** and click on the **team name**. Under **Team Role**, click the **dropdown** and select a new role. 

All other edits to Schedules, Escalation Policies and Services can be made on their corresponding tabs:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/22fe4cf-teams-edit-roles.png",
        "teams-edit-roles.png",
        1988,
        628,
        "#f7f5f5"
      ]
    }
  ]
}
[/block]
##Manage Primary Team

Some organizations may want users to have primary teams for billing purposes. To designate a user's primary team:

1. Navigate to **Configuration**, select **Users** and click the **name** of the desired user. 
2. Select the **Permissions & Teams** tab and click the **Manage primary team** button in the Teams & Team Roles section. 
3. On the next screen you will have the option to search and select the user's desired primary team, or you may remove one by clicking the **Unset primary team** button. Click **Confirm Selection** to save. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/204583a-teams-manage-primary-team.png",
        "teams-manage-primary-team.png",
        1114,
        552,
        "#f4f2f2"
      ]
    }
  ]
}
[/block]
4. You will now be able to see the user's primary team in the Teams & Team Roles section.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8808902-teams-primary-team-saved.png",
        "teams-primary-team-saved.png",
        474,
        232,
        "#ededee"
      ],
      "sizing": "80"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "A user must already be a team member of the selected primary team. You may add users to a  New Team or add a user to an existing team through the Teams page to select a primary team that the user is not already on."
}
[/block]
##Filter by Teams

To filter the view in PagerDuty use the drop-down in the top right corner to quickly bring back team-specific information. You can choose to view all teams, any teams you're associated with, or a specific user, depending on your permissions.
[block:callout]
{
  "type": "info",
  "body": "If a user is not on any teams they will still be visible by selecting **All Teams**.",
  "title": "Note"
}
[/block]
To quickly see all users in a team go to the team drop-down menu and select the DevOps team:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b5db5b5-CreatingTeams_img5.png",
        "CreatingTeams_img5.png",
        318,
        257,
        "#e9d4d1"
      ]
    }
  ]
}
[/block]
Go to **Configuration** → **Users** and only Users associated with that selected team will appear.

Similarly, you can filter escalation policies associated with that team by selecting **Escalation Policies** from the **Configuration** menu as well as the **Incidents** page.
[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "There is a limit of 500 users per team."
}
[/block]