---
title: "Configuring User Profiles"
excerpt: ""
---
[block:api-header]
{
  "title": "Changing or Resetting Passwords"
}
[/block]
- [Reset Password](/docs/configuring-a-user-profile#section-reset-password)
- [Change Password](/docs/configuring-a-user-profile#section-change-password)
- [Change Another User's Password](/docs/configuring-a-user-profile#section-change-another-user-s-password)

##Reset Password

If you forgot your password, you can reset it by sending yourself a password reset email.
[block:callout]
{
  "type": "info",
  "body": "You must be logged out to reset your password.",
  "title": "Note"
}
[/block]
1. Access your account's login page (i.e. https://subdomain.pagerduty.com) and click **Forgot your password?**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a29a23a-login.png",
        "login.png",
        343,
        345,
        "#e2e9dd"
      ]
    }
  ]
}
[/block]
2. Enter your email address and click **Reset Password**.
[block:callout]
{
  "type": "info",
  "body": "If using SSO, you will need to contact your account owner to reset your password with your identity provider.",
  "title": "Note"
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7eb777b-Reset.png",
        "Reset.png",
        343,
        345,
        "#1bbb0f"
      ]
    }
  ]
}
[/block]
3. You will receive an email containing a link to reset your password.
[block:callout]
{
  "type": "info",
  "body": "The password reset URL expires 2 hours after it is sent out.",
  "title": "Note"
}
[/block]
4. Follow the on-screen instructions to reset your password.

##Change Password

If you know your password and are able to log in, you can change your password from your user profile.
1. Access your user profile by selecting your profile icon from the top right corner of your screen and select **My Profile** from the dropdown.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/46be274-my_profile.png",
        "my_profile.png",
        1326,
        187,
        "#f0f0f7"
      ]
    }
  ]
}
[/block]
2. Navigate to the **User Settings** tab and click **Change Password…**
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/10f1b52-user_settings.png",
        "user_settings.png",
        1066,
        290,
        "#296d59"
      ]
    }
  ]
}
[/block]
3. Follow the on screen instructions to change your password and click **Save**.

##Change Another User's Password

Users with an Account Owner or Admin user role have the ability to change another user's password for them.
1. Navigate to **Configuration → Users**.
2. Click on the name of the user who's password you want to change.
3. Click the **User Settings** tab and select **Change Password…** 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6d1ae89-user_settings-1.png",
        "user_settings-1.png",
        1066,
        290,
        "#296d59"
      ]
    }
  ]
}
[/block]
4. Enter *your* password, and then enter the user's new password and click **Save**.
[block:api-header]
{
  "title": "Temporarily Disable Notifications"
}
[/block]
If you go on vacation or will be unavailable for a period of time we recommend [creating an override](/docs/editing-schedules#section-create-and-delete-overrides) for any schedule for which you are on-call. This ensures that there is coverage if an incident is assigned to you while you are not available to address the incident.

You can create overrides in the PagerDuty website, mobile app, or [via our API](doc:configuring-a-user-profile). You can also use [this Python script](https://gist.github.com/mdcollins05/8c639696a9608a76b755) to schedule overrides through our API when a user goes on vacation.

If you want to make sure that you do not receive any PagerDuty notifications when you go on vacation or are unavailable to be on-call, you will need to remove your notification rules.

To do this:
1. Click on your user icon at the top right corner of the screen and click on My Profile.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5369740-my_profile.png",
        "my_profile.png",
        474,
        221,
        "#eaeded"
      ]
    }
  ]
}
[/block]
2. In your profile, click on the **Notification Rules** tab.
3. Under **When an incident is assigned to me...**, remove your notification rules by clicking on the **X** button to the right of each rule.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/68435c1-Notification_Rules.png",
        "Notification_Rules.png",
        881,
        489,
        "#dfe7eb"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "Removing notification rules does NOT mean that incidents cannot be assigned to you. Incidents can still be assigned and [delegated](/docs/adding-users-to-existing-incidents#section-reassign-or-delegate-an-incident) to you even if you do not have any notification rules as long as you are still on-call on a schedule or included in an escalation policy. By deleting your Notification Rules, you will simply avoid being notified for these incidents.\n\nAlso note that removing your notification rules will NOT remove your contact methods. When you would like to receive PagerDuty notifications again, you can go back to your profile page and re-add your notification rules.",
  "title": "Note"
}
[/block]

[block:api-header]
{
  "title": "User Profiles"
}
[/block]
The user profile is where you are able to configure a variety of different things, including: individual user settings, contact information, notification rules and on-call handoff notifications, and profile settings.

To access your user profile, select your profile icon from the top right corner of your screen and select **My Profile** from the dropdown.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7eaa12b-my_profile.png",
        "my_profile.png",
        356,
        211,
        "#e8eee9"
      ]
    }
  ]
}
[/block]
##Contact Information

The Contact Information tab is where users can update phone numbers, SMS numbers and email addresses where they would like to be contacted when an incident is assigned to them.

Users can also view which devices are registered to their user profile to receive push notifications. Refer to this article to learn more about [adding a mobile device to receive push notifications](/docs/mobile-app#section-adding-a-mobile-device-for-push-notifications).

Users can edit their Name, Title, Bio, and set the Time Zone that schedules, incident logs, and on call times are shown in for their specific user profile.

###Add a Contact Method
1. Click **Add Phone Number**, **Add SMS Number**, or **Add Email Address**. You're able to include up to 10 different contact methods.
2. Enter contact information into the field. You have the option to configure a [phone number with an extension](/docs/notification-settings#section-dialing-extensions-and-introducing-a-delay-before-voicemail) if needed.
3. Click **Save**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5bff8e7-contact_info.png",
        "contact_info.png",
        1072,
        554,
        "#30645f"
      ]
    }
  ]
}
[/block]
###View Recent User Activity

Underneath a user's contact information, you can view their activity for the past 14 days. This includes information about incidents that the user acknowledged, resolved, or manually triggered through the web application.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/138db3c-recent_activity.png",
        "recent_activity.png",
        1069,
        301,
        "#f7f6f5"
      ]
    }
  ]
}
[/block]
##Hiding Contact Information
The Account Owner can optionally hide users' contact info (phone/SMS numbers and email addresses) in the web UI under **Configuration → Account Settings → Account Details**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6e376f3-dcd5f92-account_settings.png",
        "dcd5f92-account_settings.png",
        1047,
        405,
        "#8c6a33"
      ]
    }
  ]
}
[/block]
With this option enabled, non-admin users will see other users' contact methods replaced mostly with asterisks (`*`).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f606d4e-f920d29-user_profile.png",
        "f920d29-user_profile.png",
        693,
        504,
        "#3f5962"
      ]
    }
  ]
}
[/block]
##Notification Rules
The **Notification Rules** tab is where users can configure where and when they will be notified when a triggered incident is assigned to them. You have the option to create unique notification rules for both [high-urgency incidents as well as low-urgency incidents](/docs/service-settings#section-high-and-low-urgency-incidents).

###Configure Notification Rules
1. Select **Add Notification Rule**.
2. Enter the number of minutes you would like to pass between the moment an incident is assigned to you and when PagerDuty sends the notification. This defaults to 0 minutes, which will notify you immediately.
3. Select the contact method that you would like to be notified on. You can use the same contact method with multiple notification rules.
4. Click **Save**.

You can read more about [best practice tips](https://community.pagerduty.com/t/top-10-best-practice-tips/826?u=jcurreee&utm_source=web&utm_campaign=kb_nav&utm_medium=link#multiple-notification-rules) for configuring notification and escalation rules on our Community Site.

###Status Update Rules
Users can configure status update rules to receive notifications every time that a high-urgency incident that is assigned to them changes status (i.e. acknowledged, resolved, or escalated).
1. Under the section titled **When any of my high-urgency incidents change...**
2. Select whether you would like to be notified when an incident is acknowledged, resolved, or escalated, then select the contact method by which you would like to be notified.
3. Click **Save**.

If a notification has not been sent to a particular contact method for an incident yet at the time that a status update rule should be triggered, a status update notification will not be sent out. If you don't receive a status update, check that the ack, resolve, or escalate happened after you received your initial alert notification to that contact method.

Note that if you acknowledge or resolve your own incident, you will not receive a status update notification even if you have a rule configured.

###On-Call Handoff Notifications

On-Call Hand Off Notifications will notify you up to 48 hours before you go on-call, off-call, or both. These notifications can only be sent as an SMS, push notification, or email.
1. Under the section titled **Before I go on-call or off-call...** click **Add On-Call Handoff Notification Rule**
2. Enter the following information:
    - The number of hours prior, that you would like to be notified.
    - Whether you want to be notified before going on-call, off-call, or both.
    - The contact method where you want to receive the notification.
3. Click **Save**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4ce4a2a-notification_rules.png",
        "notification_rules.png",
        1077,
        1008,
        "#334e5b"
      ]
    }
  ]
}
[/block]
##User Settings
- **Login Email** — This is the email that you use specifically to login to PagerDuty. This may be different from what you have configured in your notification rules. You can edit this by clicking the edit button to the left.
- **Password** — You can change your password by clicking **Change password…**
[block:callout]
{
  "type": "info",
  "body": "If you are an Account Owner or Admin, you can [change another user's password](/docs/configuring-a-user-profile#section-change-another-user-s-password) here.",
  "title": "Note"
}
[/block]
- **Role** — This is the user role associated with your user profile. You can read more about [user roles](/docs/user-roles#section-user-roles-in-your-account). Only the account owner or an admin on the account can update this.
- **Schedule Color** — Each user has a color associated with their profile which is used in the on-call schedule to quickly recognize the user. You can change this by clicking the edit button to the left.
- **Calendar** — This is for syncing your on-call schedules to calendar applications like Google Calendar, Apple Calendar, etc. We have instructions on [exporting your on-call schedules to your calendar application](/docs/schedules-and-exterior-tools#section-exporting-on-call-schedules-to-a-calendar-app).
- **Photo** — PagerDuty uses [Gravatar](http://en.gravatar.com/) to manage profile photos.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/04c0246-user_settings.png",
        "user_settings.png",
        1067,
        559,
        "#2f545c"
      ]
    }
  ]
}
[/block]
# Revoking Application Access
If you have authorized the PagerDuty mobile app or a third-party application, go to your user profile to view which apps you have authorized and to revoke access. All applications have continued access to your PagerDuty account and data once authorized.

On your user profile under **User Settings → Applications**, authorized apps are listed by name along with the date the authorization was created:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dadf3ea-user-profile-applications.png",
        "user-profile-applications.png",
        2118,
        286,
        "#f9f6f6"
      ]
    }
  ]
}
[/block]
Click the red **Revoke** button to revoke the application’s access to your account.
The page will refresh and you will see a green banner confirming the application’s authorization has been revoked:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1f0d98b-user-profile-app-revoked.png",
        "user-profile-app-revoked.png",
        2252,
        378,
        "#bec4c3"
      ]
    }
  ]
}
[/block]