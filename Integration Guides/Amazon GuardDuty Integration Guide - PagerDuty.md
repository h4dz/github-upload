---
title: "Amazon GuardDuty Integration Guide | PagerDuty"
excerpt: "Integration Guide for Amazon GuardDuty"
---
#Integration Overview

PagerDuty’s integration with Amazon GuardDuty allows you to automate response workflows for  security issues that could affect your AWS infrastructure. PagerDuty ensures that the right people are notified about things like unauthorized behavior, and you can use PagerDuty’s alert grouping to reduce noise by grouping similar alerts into a single issue. This is a one-way integration, sending findings to PagerDuty.

Follow the instructions below to configure Amazon GuardDuty with PagerDuty. If you have any questions or need any assistance, please contact our support team at <a href="mailto:support@pagerduty.com">support@pagerduty.com</a>.

# In PagerDuty 

There are two ways that Amazon GuardDuty can be integrated with PagerDuty: via Global Event Routing or through an integration on a PagerDuty Service.

##Integrating with Global Event Routing

Integrating with Global Event Routing may be beneficial if you want to build different routing rules based on the payload coming from AWS. If you would like to learn more, please visit our article on [Global Event Routing](https://support.pagerduty.com/docs/global-event-routing).  

1. From the **Configuration** menu, select **Event Rules**
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6d9e643-PHD-Event-Rules.png",
        "PHD-Event-Rules.png",
        1780,
        1114,
        "#b8bbc0"
      ]
    }
  ]
}
[/block]
2. On the Event Rules screen, copy your **Integration Key**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1605bcd-PHD-Global-Event-Rules-Key.png",
        "PHD-Global-Event-Rules-Key.png",
        2222,
        1184,
        "#f8f8f7"
      ]
    }
  ]
}
[/block]
3. Once you have your **Integration Key**, the **Integration URL** will be:

`https://events.pagerduty.com/x-ere/[YOUR_INTEGRATION_KEY_HERE]`

You can now proceed to the [In the AWS Management Console](https://support.pagerduty.com/v1/docs/aws-guardduty-integration-guide#section-in-the-aws-management-console) section below. 

##Integrating with a PagerDuty Service

Integrating with a PagerDuty Service directly can be beneficial if you don’t need to route alerts from AWS to different responders based on the event payload. You can still use [service-level event rules](https://support.pagerduty.com/docs/event-management#section-configure-event-rules-for-a-service) to perform actions such as suppressing.

1. From the **Configuration** menu, select **Services**.
2. On your Services page: If you are creating a new service for your integration, click **+Add New Service**. It is recommended that you create a service specifically for Amazon GuardDuty notifications.

If you are adding your integration to an existing service, click the name of the service you want to add the integration to. Then click the **Integrations** tab and click the **+New Integration** button.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8f1833e-GuardDuty-Add-New-Service.png",
        "GuardDuty-Add-New-Service.png",
        1688,
        790,
        "#b2b7bb"
      ],
      "caption": ""
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/26953c0-GuardDuty-New-Integration.png",
        "GuardDuty-New-Integration.png",
        1652,
        200,
        "#f2f8f2"
      ]
    }
  ]
}
[/block]
3. Select Amazon GuardDuty from the** Integration Type** menu and enter an **Integration Name**.
If you are creating a new service for your integration, in General Settings, enter a **Name** for your new service. Then, in Incident Settings, specify the** Escalation Policy**, **Notification Urgency**, and **Incident Behavior** for your new service.
4. Click the **Add Service** or** Add Integration** button to save your new integration. You will be redirected to the Integrations page for your service.
5. Copy the** Integration URL** for your new integration.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6e9a2c4-GuardDuty-Integration-URL.png",
        "GuardDuty-Integration-URL.png",
        1692,
        384,
        "#f5f2f2"
      ]
    }
  ]
}
[/block]
# In the AWS Management Console

1. In the SNS console, click **Create Topic**. This will be used to route alerts to PagerDuty from AWS.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4a319ab-GuardDuty-SNS-Create-Topic.png",
        "GuardDuty-SNS-Create-Topic.png",
        1701,
        654,
        "#f7f7f7"
      ]
    }
  ]
}
[/block]
2. Enter a **Topic name** and **Display name**, then click **Create topic**. You may want to name your topic after your PagerDuty service’s name.
3. Now that your topic has been created, click **Create Subscription**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7400287-GuardDuty-Create-Subscription.png",
        "GuardDuty-Create-Subscription.png",
        1558,
        344,
        "#edecec"
      ]
    }
  ]
}
[/block]
4. Make sure **HTTPS** is the selected Protocol. Paste your **SNS Webhook URL** from step 5 (above) into the **Endpoint** field and click **Create Subscription**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/160b49c-GuardDuty-Create-Subscription-2.png",
        "GuardDuty-Create-Subscription-2.png",
        1790,
        694,
        "#f3f1f1"
      ]
    }
  ]
}
[/block]
5. Your subscription should be automatically confirmed. Click the refresh icon to make sure the **Subscription ID** is not *PendingConfirmation*.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3c37dd4-GuardDuty-Pending-Confirmation.png",
        "GuardDuty-Pending-Confirmation.png",
        3035,
        478,
        "#f2f2f2"
      ]
    }
  ]
}
[/block]
6. Navigate to the Amazon GuardDuty console. If this is your first time [setting up this service](https://docs.aws.amazon.com/guardduty/latest/ug/guardduty_settingup.html#guardduty_enable-gd), search for GuardDuty, and click Enable GuardDuty. 
7. Once you have enabled GuardDuty, you can begin building CloudWatch Event Rules to send alerts to PagerDuty. Navigate to the CloudWatch console.
8. Select **Events**, then click **Get Started** to create a rule. One or more rules can be created to send specific alerts to PagerDuty when a GuardDuty finding is opened.
9. Select **GuardDuty** as the **Service Name**, then select **GuardDuty Finding** as the Event Type.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1c619e7-GuardDuty-Create-Rule.png",
        "GuardDuty-Create-Rule.png",
        1158,
        1216,
        "#f2f1f0"
      ],
      "sizing": "full"
    }
  ]
}
[/block]
10. Click **Add a target** and select **SNS topic**, then select **Your Topic Name** (the SNS topic you created above in step 1) and then click **Configure Details**.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/17dfcd9-GuardDuty-Targets.png",
        "GuardDuty-Targets.png",
        1563,
        532,
        "#f6f2f3"
      ]
    }
  ]
}
[/block]
11. Assign a Name like *GuardDuty-to-PD-Findings* and click **Create Rule**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/068719a-GuardDuty-Configure-Rule.png",
        "GuardDuty-Configure-Rule.png",
        1562,
        726,
        "#f4f6f8"
      ]
    }
  ]
}
[/block]
12. To ensure configuration was successful, navigate back to the Amazon GuardDuty console to generate sample findings, which should trigger sample events in PagerDuty. Select **Settings**, then select **Generate Sample Findings** and then click **Findings** in the left navigation bar. You will see the sample findings that have been generated. In PagerDuty, you will see the correlating sample alert. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/390393a-GuardDuty-Sample-Findings.png",
        "GuardDuty-Sample-Findings.png",
        2396,
        1244,
        "#f6f6f6"
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
        "https://files.readme.io/3488e87-GuardDuty-Findings.png",
        "GuardDuty-Findings.png",
        2282,
        730,
        "#f0ede7"
      ]
    }
  ]
}
[/block]
Congratulations, you have now integrated Amazon GuardDuty with PagerDuty! For more information on how to adjust settings to deduplicate events within PagerDuty, please visit our article on [Event Management](https://support.pagerduty.com/docs/event-management).