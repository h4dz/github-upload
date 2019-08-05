---
title: "Contextual Search - Tagging"
excerpt: ""
---
Contextual Search uses tags to enable faster searches for objects such as teams, escalation policies and users. Large organizations can use tags to add metadata to indirectly related objects and identify their dotted-line relationships. Contextual Search also helps Responders and Managers navigate to the correct objects and reassign incidents quickly and easily. 
[block:api-header]
{
  "title": "Create and Add Tags"
}
[/block]
Tags should be created for each object category (i.e. teams, escalation policies and users) that you would like them applied to, as they are siloed separately and do not transfer. For example, if you add a “Payments” tag to a team, this will not appear as an escalation policy tag, and it will not transfer to any individual user on that team. If you would like a “Payments” tag available for all objects, you will need to add it to a team, escalation policy and a user.
[block:callout]
{
  "type": "warning",
  "title": "Required User Permissions",
  "body": "**Create Tags**: Admin [roles](https://support.pagerduty.com/docs/user-roles), Global Admin and Account Owner [base roles](https://support.pagerduty.com/docs/advanced-permissions#section-base-roles) can create and delete tags by default. Global Admins and Account Owners can also opt to allow Managers to create tags by navigating to **Configuration** → **Account Settings** → **Tagging** tab and selecting **Team Managers can create new tags (in addition to Account Owner and Global Admins)**.\n\n**Add Existing Tags**: Admin [roles](https://support.pagerduty.com/docs/user-roles) and Manager, Global Admin and Account Owner [base roles](https://support.pagerduty.com/docs/advanced-permissions#section-base-roles) can add existing tags to objects. If your base role is lower but you have a Manager [team role](https://support.pagerduty.com/docs/advanced-permissions#section-team-roles), you will only be able to add tags to your team, its escalation policies and its users.\n\nIf you're not sure what role you have, or if you need your permissions adjusted, visit our sections on [Checking Your User Role](https://support.pagerduty.com/v1/docs/user-roles#section-checking-your-user-role) or [Changing User Roles](https://support.pagerduty.com/docs/user-roles#section-changing-user-roles)."
}
[/block]
To Create or Add a Tag:

1. Navigate to **Configuration** and select **Teams**, **Escalation Policies** or **Users** depending on what object you would like to create tags for or add existing tags to.
2. For teams and escalation policies, click the :fa-cog: icon and select :fa-edit:**Edit**. For users, click the user name, select the **User Settings** tab and click the :fa-edit: icon.
3. In the Tags field (pictured by each object configuration screen below):
**To create a tag**: enter a name into the field, hit return/enter on your keyboard and then click **Save**. 
**To add an existing tag**: type the tag name you’re searching for and select it from the dropdown, or browse the dropdown for your tag and then click **Save**.

**Team Tags**:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1117b2b-contextual-search-add-tags-team.png",
        "contextual-search-add-tags-team.png",
        1706,
        940,
        "#f6f7f4"
      ]
    }
  ]
}
[/block]
**Escalation Policy Tags**:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/30057bc-contextual-search-create-ep-tag.png",
        "contextual-search-create-ep-tag.png",
        1706,
        728,
        "#f5f7f4"
      ]
    }
  ]
}
[/block]
**User Tags**:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/18d820b-contextual-search-add-user-tags.png",
        "contextual-search-add-user-tags.png",
        1704,
        640,
        "#f4f5f1"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Filter Objects by Tag"
}
[/block]
1. Navigate to **Configuration** and select **Teams**, **Escalation Policies** or **Users** depending on which object you would like to filter.
2. Next to the search bar, click the :fa-filter:**Filter By Tags** button and search for your tag or browse the dropdown for it. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/049b2d2-contextual-search-filter-tags-team.png",
        "contextual-search-filter-tags-team.png",
        1732,
        624,
        "#f8f9fa"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Reassign an Incident Using Tags"
}
[/block]
1. On an incident, click the **Reassign** button. 
2. On the **Reassigning incident to…** screen, enter the tag name or browse tags in the Choose tags field. This will filter escalation policies, users and escalation levels that have this tag applied. Select your desired escalation policy, user or escalation level and then click **Reassign**. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a9fdc07-contextual-search-reassign-incident.png",
        "contextual-search-reassign-incident.png",
        1105,
        428,
        "#f2f6f9"
      ]
    }
  ]
}
[/block]