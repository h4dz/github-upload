---
title: "User Roles"
excerpt: ""
---
[block:callout]
{
  "type": "info",
  "title": "User Role Tiers",
  "body": "PagerDuty has two tiers of user roles depending on your account's plan. To determine which tier your role belongs to, click the **user icon** in the upper right of your account and select **My Profile**. If you see a tab that says **Permissions & Teams**, please visit our article on [Advanced Permissions](https://support.pagerduty.com/docs/advanced-permissions). If you only see the **User Settings** tab, please continue to use this article for reference."
}
[/block]

[block:api-header]
{
  "title": "User Roles in Your Account"
}
[/block]

[block:parameters]
{
  "data": {
    "h-1": "Stakeholder*",
    "h-2": "Limited User",
    "h-3": "User",
    "h-4": "Admin",
    "h-5": "Account Owner",
    "0-0": "View:\n- User profiles\n- Incidents\n- Schedules\n- Escalation policies\n- Services\n- Analytics",
    "1-0": "Subscribe to incidents",
    "2-0": "Be added on schedules and escalation policies",
    "3-0": "Create overrides for schedules that the user is on-call for",
    "4-0": "Trigger, acknowledge, reassign, and resolve incidents",
    "5-0": "Add/edit/delete:\n- On-call schedules\n- Escalation policies\n- Services\n- Maintenance windows\n- Teams\n- Response plays",
    "6-0": "Add new users",
    "7-0": "Delete users (cannot delete the Account Owner)",
    "8-0": "Edit a user's profile/password",
    "9-0": "Create/delete REST API keys",
    "10-0": "Access billing information",
    "11-0": "Cannot be deleted",
    "12-0": "Change the account owner",
    "13-0": "Enable and edit Single Sign-On (SSO) properties\\*",
    "14-0": "Delete the account",
    "0-1": "✓",
    "0-2": "✓",
    "0-3": "✓",
    "0-4": "✓",
    "0-5": "✓",
    "1-1": "✓ **",
    "1-2": "✓",
    "1-3": "✓",
    "1-4": "✓",
    "1-5": "✓",
    "2-2": "✓",
    "2-3": "✓",
    "2-4": "✓",
    "2-5": "✓",
    "3-2": "✓",
    "3-3": "✓",
    "3-4": "✓",
    "3-5": "✓",
    "4-2": "✓",
    "4-3": "✓",
    "4-4": "✓",
    "4-5": "✓",
    "5-3": "✓",
    "5-4": "✓",
    "5-5": "✓",
    "6-4": "✓",
    "6-5": "✓",
    "7-4": "✓",
    "7-5": "✓",
    "8-4": "✓",
    "8-5": "✓",
    "9-4": "✓",
    "9-5": "✓",
    "10-5": "✓",
    "11-5": "✓",
    "12-5": "✓",
    "13-5": "✓",
    "14-5": "✓",
    "h-6": "Account Owner",
    "0-6": "✓",
    "1-6": "✓",
    "2-6": "✓",
    "3-6": "✓",
    "4-6": "✓",
    "5-6": "✓",
    "6-6": "✓",
    "7-6": "✓",
    "8-6": "✓",
    "9-6": "✓",
    "10-6": "✓",
    "11-6": "✓",
    "12-6": "✓",
    "13-6": "✓",
    "14-6": "✓"
  },
  "cols": 6,
  "rows": 15
}
[/block]
\**Available on Platform Business and Enterprise pricing plans.*
\*** Stakeholder Subscriptions to incidents are only available with our Modern Incident Response package. Please contact our [Sales Team](https://www.pagerduty.com/contact-sales/) if you would like to upgrade to a plan with this feature.*

##Stakeholder Users

Stakeholder users are available by default on Enterprise plans, and can [purchased as add-on users](https://www.pagerduty.com/pricing/) on Platform Team and Platform Business plans. Stakeholders can view objects in an account, but cannot make modifications. The intended use case for a Stakeholder is to be added as a [Subscriber](doc:adding-users-to-existing-incidents#section-add-and-notify-subscribers) to an incident — they will receive updates about the incident, but cannot take any action. Subscriptions to incidents are only available for Stakeholders with our Modern Incident Response package. Please contact our [Sales Team](https://www.pagerduty.com/contact-sales/) if you would like to upgrade to a plan with this feature.

Stakeholder licenses are not billed the same as full users. Please contact your Account Manager for more information.
[block:api-header]
{
  "title": "Checking Your User Role"
}
[/block]
To check what role you have, click the **user icon** in the upper right of the web app, select **My Profile**. Depending on your account's plan, your user role information will be found in the following tabs:
- Starter and Platform Team plans will only have a **User Settings** tab, and you will find your **Role** information there. These role types are standard [User Roles](https://support.pagerduty.com/docs/user-roles#section-user-roles-in-your-account).
- Platform Business and Enterprise plans will have an additional **Permissions & Teams** tab where you can find information about your [Base Role](https://support.pagerduty.com/docs/advanced-permissions#section-base-roles) and any [Team Role(s)](https://support.pagerduty.com/docs/advanced-permissions#section-team-roles) or [Object Role(s)](https://support.pagerduty.com/docs/advanced-permissions#section-object-roles) that you may have. These role types are [Advanced Permissions](https://support.pagerduty.com/docs/advanced-permissions).
[block:api-header]
{
  "title": "Changing User Roles"
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "Required User Permissions",
  "body": "Admin, Global Admin and Account Owner roles.\n\nIf you're not sure what role you have, please read the above section, [Checking Your User Role](https://support.pagerduty.com/v1/docs/user-roles#section-checking-your-user-role)."
}
[/block]
If you would like your role changed, please contact an Admin, Global Admin or Account Owner on your PagerDuty account. Only the Account Owner can change their own role by [transferring account ownership](doc:change-account-owner) to another user in the account.

To change a user's role:
1. Go to **Configuration → Users**.
2. Click the name of the user  you would like to update.
3. On their profile page, click the **User Settings** tab.
4. Click on the **Edit** icon to the right of the **Role** section. Select a new role from the dropdown.
5. Click **Save**.