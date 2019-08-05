---
title: "AWS Personal Health Dashboard Integration Guide | PagerDuty"
excerpt: "Integration Guide for AWS Personal Health Dashboard"
---
#Integration Overview

PagerDuty’s integration with AWS Personal Health dashboard enables you to immediately receive notifications about problems with AWS Services, via PagerDuty. This can be especially helpful when there are infrastructure problems that may be impacting your services. This is a one-way integration, sending both issues and scheduled changes to PagerDuty.

Follow the instructions below to configure AWS Personal Health Dashboard with PagerDuty. If you have any questions or need any assistance, please contact our support team at <a href="mailto:support@pagerduty.com">support@pagerduty.com</a>.

# In PagerDuty 


There are two ways that AWS Personal Health Dashboard can be integrated with PagerDuty: via Global Event Routing or through an integration on a PagerDuty Service.

##Integrating with Global Event Routing

Integrating with Global Event Routing may be beneficial if you want to build different routing rules based on the payload coming from AWS. If you would like to learn more, please visit our article on [Global Event Routing](https://support.pagerduty.com/docs/global-event-routing). 

1. From the **Configuration** menu, select **Event Rules**. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/84e963c-PHD-Event-Rules.png",
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
        "https://files.readme.io/e6897a4-PHD-Global-Event-Rules-Key.png",
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

You can now proceed to the [In the AWS Management Console](https://support.pagerduty.com/v1/docs/aws-personal-health-dashboard#section-in-the-aws-management-console) section below. 

##Integrating with a PagerDuty Service

Integrating with a PagerDuty Service directly can be beneficial if you don’t need to route alerts from AWS to different responders based on the event payload. You can still use [service-level event rules](https://support.pagerduty.com/docs/event-management#section-configure-event-rules-for-a-service) to perform actions such as suppressing.

1. From the **Configuration** menu, select **Services**.
2. On your Services page: If you are creating a new service for your integration, click **+Add New Service**. It is recommended that you create a service specifically for AWS Personal Health Dashboard notifications.
If you are adding your integration to an existing service, click the name of the service you want to add the integration to. Then click the **Integrations** tab and click the **+New Integration** button.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c410120-GuardDuty-Add-New-Service.png",
        "GuardDuty-Add-New-Service.png",
        1688,
        790,
        "#b2b7bb"
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
        "https://files.readme.io/ce4c33a-GuardDuty-New-Integration.png",
        "GuardDuty-New-Integration.png",
        1652,
        200,
        "#f2f8f2"
      ]
    }
  ]
}
[/block]
3. Select AWS Personal Health Dashboard from the** Integration Type** menu and enter an **Integration Name**.
If you are creating a new service for your integration, in General Settings, enter a **Name** for your new service. Then, in Incident Settings, specify the** Escalation Policy**, **Notification Urgency**, and **Incident Behavior** for your new service.
4. Click the **Add Service** or** Add Integration** button to save your new integration. You will be redirected to the Integrations page for your service.
5. Copy the **Integration URL** for your new integration.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d129b6c-GuardDuty-Integration-URL.png",
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
        "https://files.readme.io/76bb974-GuardDuty-SNS-Create-Topic.png",
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
        "https://files.readme.io/79c4727-GuardDuty-Create-Subscription.png",
        "GuardDuty-Create-Subscription.png",
        1558,
        344,
        "#edecec"
      ]
    }
  ]
}
[/block]
4. Make sure **HTTPS** is the selected Protocol. Paste your **Integration URL** from step 5 (above) into the **Endpoint** field and click **Create Subscription**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ce086bb-GuardDuty-Create-Subscription-2.png",
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
        "https://files.readme.io/507bcbe-GuardDuty-Pending-Confirmation.png",
        "GuardDuty-Pending-Confirmation.png",
        3035,
        478,
        "#f2f2f2"
      ]
    }
  ]
}
[/block]
6. To navigate to the AWS Personal Health Dashboard, click on the **Alerts** icon in the top navigation bar, then select **View all alerts**, and then select **Dashboard** in the left navigation bar.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/683ae05-PHD-Alerts.png",
        "PHD-Alerts.png",
        1806,
        486,
        "#d0d2d4"
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
        "https://files.readme.io/2ad11e1-PHD-Dashboard-Left-Nav.png",
        "PHD-Dashboard-Left-Nav.png",
        2818,
        550,
        "#f3f3f3"
      ]
    }
  ]
}
[/block]
7. To create an [alarm](https://docs.aws.amazon.com/health/latest/ug/cloudwatch-events-health.html), click **Set up notifications with CloudWatch Events** in the upper right hand corner. Enter **Health** as the **Service Name**. 
Decide if you want to route all AWS Personal Health Dashboard notifications or only ones for specific services. For all events, set **Event Type** to **All Events** or alternatively select **Specific Health events** then choose the services you are interested in.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1802734-PHD-Create-a-Rule.png",
        "PHD-Create-a-Rule.png",
        1586,
        1546,
        "#f7f4f4"
      ]
    }
  ]
}
[/block]
8. Click **Add target**, select **SNS topic** in the dropdown menu, select the **Topic** you created above (in steps 1-5) and then click **Configure details**. In the **Configure rule details** section, assign a name and optional description for the rule, then click **Create Rule**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ace7391-PHD-Add-Target.png",
        "PHD-Add-Target.png",
        1354,
        554,
        "#faf5f5"
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
        "https://files.readme.io/9335e40-PHD-Configure-Rule-Details.png",
        "PHD-Configure-Rule-Details.png",
        1582,
        706,
        "#f5f6f8"
      ]
    }
  ]
}
[/block]
9. Now that you have configured CloudWatch to send AWS Personal Health Dashboard notifications to PagerDuty, your responders will immediately be notified when AWS is experiencing problems.

Congratulations, you have now integrated AWS Personal Health Dashboard with PagerDuty! For more information on how to adjust settings to deduplicate events within PagerDuty, please visit our article on [Event Management](https://support.pagerduty.com/docs/event-management).