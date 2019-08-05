---
title: "Create Your First Notification"
excerpt: ""
---
This guide discusses everything you need to know to set up your PagerDuty profile and receive your first notification. After reading this guide you should be familiar with the following topics:

* Setting up your PagerDuty user profile.
* Entering contact information and notification rules in your user profile.
* How to receive your first notification from PagerDuty.
* The general layout of the PagerDuty application. 

## Step 1: Add Contact Methods to your Profile

Contact methods are the different ways in which you would like to be contacted (phone, SMS, email or push notification).

1. Click on your user icon at the top right corner of the screen and click on **My Profile**.

2. Under the **Contact Information** tab, click **Add Phone Number**, **Add SMS Number**, or **Add Email Address**.

3. Enter your contact information in the fields. For push notifications, your mobile device will be listed as a Push contact method once you have installed the app and logged in to your PagerDuty account through the app.

4. Click **Save** for each newly added contact method.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/258f668-Contact_Information.png",
        "Contact Information.png",
        650,
        525,
        "#dce5ea"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "There is a maximum of 10 total contact methods that can be added to any individual profile (for example, you can add 5 phone numbers and 5 SMS numbers, or 2 email addresses, 2 phone numbers, and 6 SMS numbers).",
  "title": "Note"
}
[/block]
## Step 2: Add Notification Rules to your Profile

Notification Rules define when and where you will be notified when an incident is assigned to you.

To set up Notification Rules:

1. In your profile, click on the **Notification Rules** tab.

2. Under **When a high-urgency incident is assigned to me...**, click **Add Notification Rule**.

3. Enter the amount of time to wait before being notified after an incident is assigned to you (0 minutes means "notify me immediately").

4. Select the Contact Method you would like to be notified by from the drop-down menu.

5. Click **Save**.

6. You can use each contact method more than once for your notification rules. For example, you can receive a phone call immediately after an incident is assigned to you, and then another phone call to the same number 5 minutes later if you have not responded to the incident. Doing this means you will receive repeated notifications for the same incident until the incident is acknowledged.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a764465-Notification_Rules.png",
        "Notification Rules.png",
        800,
        250,
        "#365e4b"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Tip",
  "body": "We recommend a minimum of 2 notification rules, one of which being a phone call, so that you do not miss a critical incident.\n\nIf a user is assigned to an incident and has a notification rule that will take effect at the same time the active escalation policy advances, then it is possible that the user will not receive a notification corresponding to that rule. PagerDuty recommends that you set up notification rules with time offsets smaller than escalation advancement timeouts, as this will ensure notification rules will take effect reliably."
}
[/block]
## Step 3: Create an Escalation Policy

Escalation policies determine who you want to notify when an incident is triggered and how you would like to escalate the incident to other users.

Since we are testing out to receive your first PagerDuty notification, we will make you the immediate escalation rule.
[block:callout]
{
  "type": "info",
  "body": "For all new PagerDuty accounts, we have already set up an escalation policy called \"Default\" where the Account Owner is the sole escalation rule. If you are the Account Owner and you see this Default escalation policy already set up for you, you can skip this step.",
  "title": "Note"
}
[/block]
1. Go to the **Configuration** menu and select **Escalation Policies**.

2. Click **New Escalation Policy** at the top right corner of the screen to add a new escalation policy OR click on the cog of an existing escalation policy and select **Edit**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/65983f7-Escalation_Policies_-_PagerDuty2.png",
        "Escalation_Policies_-_PagerDuty2.png",
        590,
        253,
        "#31954c"
      ]
    }
  ]
}
[/block]
3. If it is a new escalation policy, name it.

4. Under **Notify the following users or schedules**, select your name from the list so that you are immediately assigned a triggered incident for this escalation policy.

5. Click **Save**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b71a518-AAATEST_-_PagerDuty.png",
        "AAATEST_-_PagerDuty.png",
        598,
        507,
        "#eceded"
      ]
    }
  ]
}
[/block]
## Step 4: Set up a Service or Integration

Services may represent an application, component, or team you wish to open incidents against. Integrations are used to integrate with your monitoring tools.

1. Go to the **Configuration** menu and select **Services**.

2. On your Services page:If you are creating a new service for your integration, click **Add New Service**.

If you are adding your integration to an existing service, click the name of the service you want to add the integration to. then click the **Integrations** tab and click the **New Integration** button.

3. Select your app from the **Integration Type** menu and enter an **Integration Name**.

If you are creating a new service for your integration, in General Settings, enter a **Name** for your new service. Then, in Incident Settings, specify the **Escalation Policy**, **Notification Urgency**, and **Incident Behavior** for your new service.

4. Select an **Integration Type**:

First, [check to see if we have an existing integration for your service](https://www.pagerduty.com/integrations). Search for your service by clicking on the drop down menu next to **Integration Type**.

If you do not see your service in the drop-down, you can select **Integrate via email**. If your service can send out email notifications, you can [create an integration email address](https://www.pagerduty.com/docs/guides/email-integration-guide) in PagerDuty that you can point your service to for your incidents.

Alternatively, you can select **Use our API directly**. If your service is able to make basic HTTP API calls, then you can interact directly with our API to trigger, acknowledge, and resolve incidents. Our [developer documentation](https://developer.pagerduty.com/docs/events-api) provides several examples of how to integrate with PagerDuty using our API.

5. Click the **Add Service** or **Add Integration** button to save your new integration. You will be redirected to the Integrations page for your service.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/135565e-RS_Updates__Adding_a_Service.png",
        "RS_Updates__Adding_a_Service.png",
        1006,
        942,
        "#42666e"
      ]
    }
  ]
}
[/block]
## Step 5: Receiving Your First Notification

Now that we have your contact methods, notification rules, escalation policy, and service set up, we are ready to trigger an incident so that you can receive your first notification!

To do this, we are going to manually trigger an incident for the service that you created:

1. Go to the **Configuration** menu and select **Services**.

2. Click on the cog to the far right column of the service.

3. Select **Trigger Incident**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a1a632a-services_trigger_incident.png",
        "services_trigger_incident.png",
        247,
        175,
        "#f2f3f2"
      ]
    }
  ]
}
[/block]
4. Enter in a Description and Details for the Incident.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f4e5dbc-manual_trigger_window.png",
        "manual_trigger_window.png",
        604,
        439,
        "#eff1f2"
      ]
    }
  ]
}
[/block]
5. Click **Open a new incident** at the bottom of the window.

6. After doing this, a red critical icon will appear next to the service and you will see that there is a triggered incident for the service.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/72ba1ad-services_trigger_incident.png",
        "services_trigger_incident.png",
        247,
        175,
        "#f2f3f2"
      ]
    }
  ]
}
[/block]
7. You should then begin to receive an email, phone call, SMS, and/or push notification depending on your notification rules established in Step 2 above.

Congratulations! You received your first notification!

From here, you can acknowledge, resolve, re-assign/escalate the incident via phone/SMS/web UI or through the mobile app.