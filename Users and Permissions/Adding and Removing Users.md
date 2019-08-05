---
title: "Adding and Removing Users"
excerpt: ""
---
[block:api-header]
{
  "type": "basic",
  "title": "Add a User"
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "Required User Permissions",
  "body": "Admin roles, Global Admin base roles or Account Owner base roles can add and delete users.\n\nIf you're not sure what role you have, or if you need your permissions adjusted, visit our sections on [Checking Your User Role](https://support.pagerduty.com/v1/docs/user-roles#section-checking-your-user-role) or [Changing User Roles](https://support.pagerduty.com/docs/user-roles#section-changing-user-roles)."
}
[/block]
To add a user: 
1. Go to **Configuration → Users**.
2. Click **Add Users** in the top right corner of the page.
3. Enter the user's name and email address.
4. Select the desired role for the user.
5. Optionally, select a team from the dropdown to add the user to this team.
6. Click **Add** — repeat steps 3 – 5 to add than one user.
7. Click **Send Invites**.

Once you click **Send Invites**, an email is sent to each user's email address. They will be prompted to accept the invitation to PagerDuty, choose a password, and set up their user profile.
[block:api-header]
{
  "type": "basic",
  "title": "Common Issues When Adding Users"
}
[/block]
There are 3 reasons why you may not be able to add a user to your account:

1. You do not have the permission to add a user based on your user role.
2. There are User Limits set on your account.
3. You are trying to add a user that already exists in the account.

## Permission Restriction

As stated above in the **Required User Permissions** callout, only Admins, Global Admins and Account Owners have permission to add users to an account. All other roles cannot add users and do not have access to the Add Users button on the Users page.

For more information on User Roles and permissions, you can refer to this article [here](https://support.pagerduty.com/docs/user-roles).

## User Limits

If you are an Account Owner or Admin and you receive an error trying to add users, you may see something similar to the message in the screenshot below (i.e. **0 Users Created. 1 User NOT Created: [Name_of_User]**):
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1ce22cd-0_users_created.png",
        "0 users created.png",
        360,
        101,
        "#f2dcdb"
      ]
    }
  ]
}
[/block]
This error is the result of having a **User Limit** or **Stakeholder Limit** on your account, or the result of attempting to add a user that already exists in the account.

User Limits are established in the Account Settings page and can only be increased by the Account Owner.

For example, if your User Limit is set to "20" and there are already 20 users on your account, then neither the Account Owner nor an Admin would be able to add additional users until the User Limit is increased.

To change or remove the User Limit:

1. Go to Configuration :fa-arrow-right: Account Settings.
2. Scroll down to the **Account Limits** section.
3. Set the desired limits, or click :fa-remove: to remove the limit entirely.
4, Click **Save changes**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/36c0b75-User_limits.png",
        "User limits.png",
        630,
        227,
        "#ecefed"
      ]
    }
  ]
}
[/block]
If you cannot see the Account Limits section on your account settings page, your account may have a user limit built into its pricing plan. In this case, please refer to [this article](https://support.pagerduty.com/docs/billing-invoices-payments#section-user-charges) to add more users.
[block:api-header]
{
  "type": "basic",
  "title": "Resend a User Invitation"
}
[/block]
You can resend an invitation to a user if they cannot locate the first email that was sent.

1. Go to Configuration :fa-arrow-right: Users.
2. Click **Resend Invite** for the applicable user.

A new invitation email will be sent directly to the email associated with their PagerDuty account. Once a user has accepted an invitation and logged in to their account, the **Resend Invite** link will no longer appear next to the user.

Only users with an Admin or Account Owner user role can resend user invites.

[block:api-header]
{
  "title": "Delete a User"
}
[/block]
To delete a user:
1. Go to **Configuration → Users**.
2. Locate the user that you would like to delete, and click **Delete**.
3. Confirm that you would like to delete them.
[block:api-header]
{
  "type": "basic",
  "title": "Common Issues When Deleting Users"
}
[/block]
There are 3 main reasons why you may not be able to delete a user on your account:

* You do not have the permission to delete a user based on your user role.
* The user is still on-call, now and/or in the future, on a schedule and/or escalation policy.
* There is at least one open incident assigned to that user.

Note: You may not delete yourself or the Account Owner. If you wish to delete yourself, you will need the Account Owner or an Admin to do so for you. If you wish to delete the Account Owner, the Account Owner must first transfer account ownership to a different user on the account, then you can go back and delete the previous owner.